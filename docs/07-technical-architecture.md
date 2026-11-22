# 7. Technical Architecture

## 7.1 Recommended stack

**Recommendation: build web-first with TypeScript and React Three Fiber, then package it for app stores with Capacitor.**
One codebase serves school Chromebooks, home tablets, phones and desktops. Three.js gives the 3D quality
described in [document 6](06-3d-visual-audio-design.md), and the browser removes install friction for schools.

| Layer | Choice | Why |
|---|---|---|
| Language | **TypeScript** | Type safety for rules, lesson data and state |
| UI framework | **React 18 + Vite** | Large ecosystem; fast builds |
| 3D rendering | **Three.js via React Three Fiber (R3F)** + **@react-three/drei** (helpers) + **@react-three/postprocessing** | Declarative 3D scenes, PBR, shadows, effects |
| Animation | **react-spring / GSAP** for 3D motion; **Rive** for 2D character animation and UI | Smooth, interruptible animation; small Rive files with state machines |
| Chess rules | **chess.js** | Proven move generation, FEN/PGN, check, mate, stalemate and draw detection |
| Chess engine | **Stockfish (WebAssembly build)** in a Web Worker | Bot opponents, hints, game review; runs offline |
| Lesson flow | **XState** state machines | Lessons are branching scripts; state machines make them testable |
| App state | **Zustand** | Lightweight global state |
| Audio | **Howler.js** | Cross-browser audio sprites |
| Internationalisation | **i18next** | Translations, plurals, right-to-left support |
| Offline | **PWA** (Workbox service worker) + **IndexedDB** (Dexie) | Learning works without internet; syncs later |
| Mobile apps | **Capacitor** (iOS and Android) | Store distribution, native AR plugins, push notifications for parents only |
| Backend | **Supabase** (Postgres, Auth, Storage, Edge Functions) or Node.js (NestJS) + Postgres | Accounts, progress sync, classrooms, content delivery |
| Content delivery | CDN for the 3D asset packs and audio | Fast streaming of kingdom packs |
| 3D content pipeline | **Blender** → glTF 2.0 (Draco/meshopt, KTX2) | Industry standard, open format |
| Analytics | Self-hosted, privacy-first (for example, PostHog self-hosted with child mode; no third-party ad SDKs) | Child-privacy compliance |

**Alternative:** **Unity** (URP) if the product becomes native-first and needs console-level effects.
Trade-offs: heavier downloads, a weaker web build, and different skills needed. The web-first approach is
recommended for the MVP.

## 7.2 System overview

```
┌──────────────────────────── Client (PWA / iOS / Android) ────────────────────────────┐
│                                                                                       │
│  UI layer (React)            3D layer (R3F / Three.js)          Character layer (Rive)│
│  menus, map, HUD,     ◀──▶   board, pieces, camera,      ◀──▶   Pip, Nova, bosses,    │
│  dialogs, dashboards         effects, overlays, AR              lip-sync to VO        │
│        ▲                              ▲                                ▲              │
│        └──────────────┬───────────────┴────────────────┬───────────────┘              │
│                       │                                │                              │
│            Lesson Runtime (XState)             Game Controller                        │
│            reads lesson files, drives          rules (chess.js), clocks,              │
│            scenes, checks answers              move validation, PGN                   │
│                       │                                │                              │
│            Adaptive Engine                     Engine Worker (Stockfish WASM)         │
│            concept mastery, spaced             bots, hints, analysis, kid-language    │
│            repetition, puzzle choice           review                                 │
│                       │                                                               │
│            Local store (IndexedDB) ── sync queue ──────────────────────┐              │
└────────────────────────────────────────────────────────────────────────┼──────────────┘
                                                                         ▼
┌──────────────────────────────── Backend ─────────────────────────────────────────────┐
│  Auth (parent/teacher accounts; child profiles without PII) · Progress sync API       │
│  Classrooms & assignments · Puzzle service · Content CMS · Asset CDN · Reports/email  │
│  Postgres · object storage · edge functions · admin console                            │
└───────────────────────────────────────────────────────────────────────────────────────┘
```

## 7.3 Key modules

| Module | Responsibility |
|---|---|
| `board3d` | Board and piece rendering, themes, picking (raycast), drag and drop, overlays (dots, arrows, heat maps), camera rigs, quality tiers |
| `chess-core` | Wrapper around chess.js: legal moves, special-move events (castle, en passant, promotion), draw detection, FEN/PGN, variants (mini-boards, Pawn Wars) |
| `engine` | Stockfish worker; bot personalities (skill level, depth, blunder probability, style); hint generation; game review classification (best, good, inaccuracy, mistake, blunder) |
| `lesson-runtime` | Loads lesson files, runs the XState machine, plays VO and animations, validates INTERACT steps, emits mastery events |
| `minigames` | Each mini-game as a plugin sharing `board3d` and `chess-core` |
| `adaptive` | Concept mastery model, spaced-repetition scheduler, puzzle selector, frustration and boredom detection |
| `progress` | Stars, XP, badges, map unlocks, certificates |
| `audio` | VO playback with subtitles, music layers, sound effects |
| `i18n` | Strings, VO file mapping, right-to-left layouts |
| `parent-teacher` | Dashboards, class management, assignments, reports |
| `ar` | WebXR and native AR placement (phase 3) |

## 7.4 Lesson scripting format

Lessons are **data, not code**, so learning designers can write and edit them in a content tool (CMS or YAML in git) without developers.
Each script in [document 4](04-lesson-scripts.md) becomes a file like this:

```yaml
id: L2.01-rook-straight-roads
level: 2
concepts: [rook-movement]
tracks: [LK, EX, AC]
estimatedMinutes: 4
kingdom: piece-valley/tower-town
steps:
  - type: scene
    camera: three-quarter-white
    fen: "8/8/8/8/3R4/8/8/8 w - - 0 1"
    characters: [captain-rook]
  - type: say
    who: captain-rook
    line: { LK: rook.intro.lk, EX: rook.intro.ex, AC: rook.intro.ac }   # i18n + VO keys
  - type: animate
    effect: rails
    from: d4
    directions: [N, S, E, W]
  - type: interact
    task: move-to
    piece: d4
    target: d7
    showLegalDots: { LK: true, EX: true, AC: false }
    onSuccess: { say: rook.good.1, fx: star-burst }
    onFail:
      illegal-direction: { say: rook.hint.straight, fx: rails-flash }
      default: { hintLadder: true }
  - type: practice
    generator: star-collector
    params: { piece: R, stars: 3, maxMoves: optimal+1 }
    repeat: 3
  - type: check
    questions:
      - { kind: tap-all-reachable, fen: "8/8/8/8/3R4/8/8/8 w - - 0 1", square: d4 }
      - { kind: yes-no, prompt: rook.q.oneMove, fen: "...", answer: false }
    passThreshold: 0.8
  - type: reward
    stars: by-accuracy
    badge: rook-rookie
    unlock: [L2.02-star-collector-rook]
```

A **lesson editor** (an internal web tool) lets designers set up positions on a 3D board, record steps, preview
the lesson in all three tracks, and validate that every position is legal (through `chess-core`).

## 7.5 Puzzles and content

- **Source:** the Lichess puzzle database (released under CC0, public domain): more than 4 million puzzles with ratings and theme tags (fork, pin, mateIn1 and so on). Filter and curate it for kids: short solutions, clear themes, no shocking positions.
- **Custom puzzles** for Levels 1–4 (movement, rule-discrimination puzzles) are authored in the lesson editor.
- **Hall of Legends:** public-domain historical games (PGN), annotated by the coaching team.
- Every puzzle has a concept tag that maps to the curriculum's concept list. This powers adaptive review.

## 7.6 Bots and engine

- Stockfish runs in a Web Worker so the UI never freezes. The lite NNUE build is used on low-end devices.
- **Bot personality** = `{ skillLevel, depth, moveTimeMs, blunderRate, preferCaptures, preferChecks, openingBook }`.
  Low-level bots pick from engine-ranked candidate moves with weighted randomness, so they make *human-like* mistakes (such as leaving a piece hanging) rather than perfect moves followed by random blunders.
- **Kid-language review:** engine evaluations are converted by rules into explanations, for example:
  - The evaluation drops by 3 or more and the moved piece is capturable → "Oops! Your knight was left unprotected on f5."
  - A missed mate in 1 → "There was a checkmate here! Can you find it?" (becomes an "Oops Replay" puzzle)
- **AI coach:** see [AI Strategy](13-ai-strategy.md) for the full design (engine facts first, LLM only for phrasing, three-tier answer path, cost and safety rules).
- **Optional AI coach (later phase):** a server-side large language model turns engine output and the position into a friendly, age-appropriate explanation. It is guard-railed (chess topics only, output filtered), off by default for under-13s unless a parent turns it on, and never chats freely.

## 7.7 Data model (core)

```
Account (parent | teacher)        id, email, role, consent_status, locale
ChildProfile                      id, account_id, nickname, avatar, birth_year, track, settings
                                  (no surname, no email, no photo)
Classroom                         id, teacher_id, name, join_code
ClassMembership                   classroom_id, child_id
LessonProgress                    child_id, lesson_id, stars, attempts, best_accuracy, completed_at
ConceptMastery                    child_id, concept_id, rating, rd, last_reviewed, next_review
PuzzleAttempt                     child_id, puzzle_id, success, time_ms, hints_used, created_at
Game                              id, child_id, opponent (bot|child), pgn, result, review_json
Badge / Unlock                    child_id, item_id, earned_at
Assignment                        id, classroom_id, content_ref, due_at
```

## 7.8 Privacy, safety and compliance

- **COPPA** (US), **GDPR / GDPR-K** (EU), **UK Age Appropriate Design Code**, **UAE PDPL** and local equivalents.
- **Play first, no account:** a child can start alone. Local profiles hold only an avatar, an age band and progress, all stored on the device, with no network identity.
- A parent or teacher account (with verifiable parental consent) is needed only for cloud sync, classrooms, purchases and reports. It sits behind the parent gate. Child profiles never store personal data (nickname + birth year only).
- No ads, no third-party trackers, no data selling. Analytics are anonymised and aggregated.
- **No free-text chat.** Friend games use invite codes, with preset emotes only ("Good game!", "Nice move!").
- Data is encrypted in transit (TLS) and at rest; the region is chosen by the account's locale.
- Content moderation for any user-generated content (for example, custom puzzles shared in classrooms).
- Right to export and delete (parent-controlled).

## 7.9 Repository layout (proposed)

```
chessmaster/
├── apps/
│   ├── client/                 # React + R3F PWA (also wrapped by Capacitor)
│   ├── lesson-editor/          # internal authoring tool
│   └── admin/                  # content & user admin
├── packages/
│   ├── chess-core/             # rules wrapper, variants, notation
│   ├── board3d/                # R3F board, pieces, overlays, cameras
│   ├── engine/                 # stockfish worker + bot personalities + review
│   ├── lesson-runtime/         # XState interpreter for lesson files
│   ├── adaptive/               # mastery model, SRS, puzzle selection
│   └── ui/                     # shared design system (buttons, dialogs, HUD)
├── content/
│   ├── lessons/                # YAML lesson scripts (level-x/...)
│   ├── puzzles/                # curated puzzle sets
│   ├── i18n/                   # strings per locale
│   └── vo/                     # voice-over manifests
├── assets/                     # source .blend, textures (Git LFS)
├── backend/                    # Supabase migrations / edge functions or NestJS
├── docs/                       # ← these planning docs
└── tests/                      # e2e (Playwright), perft, lesson validation
```

## 7.10 Quality assurance

| Test type | Tooling | Covers |
|---|---|---|
| Rules correctness | Vitest + **perft** suites + the edge-case list in [2.14](02-chess-rules-reference.md#214-rules-engine-edge-cases-qa-checklist) | Move generation, special moves, draws |
| Lesson validation | A CI script that loads every lesson file | Legal positions, answers reachable, i18n and VO keys present |
| Unit and component tests | Vitest + React Testing Library | UI logic, adaptive engine |
| End-to-end tests | Playwright (desktop + mobile emulation) | Onboarding, lesson flows, purchases (if any), parent hub |
| Visual regression | Playwright screenshots of key 3D scenes | Rendering regressions |
| Performance | A device lab (low, mid and high tiers) + automated frame-time capture | FPS budgets, memory, load time |
| Accessibility | axe-core + manual screen-reader passes | WCAG 2.2 AA for the UI |
| Usability | Moderated play-tests with kids in each age band (with parental consent) | Comprehension, fun, frustration points, and **adult-intervention count** (target: zero; see [11](11-self-guided-learning.md)) |
