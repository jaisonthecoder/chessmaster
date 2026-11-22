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
| Analytics | First-party, privacy-reviewed event pipeline (events sent to our own backend and stored in Postgres or a warehouse we control); no third-party analytics or ad SDKs in the child app | Required by app-store kids-category rules and children's privacy law |

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
| `chess-core` | Two layers. **Game layer:** chess.js for standard games (legal moves, special moves, FEN/PGN) plus our own rules for what chess.js lacks (fivefold repetition, the 75-move rule, claim-vs-automatic draws, timeout vs mating material, blocked-pawn dead positions). **Playground layer:** our own move generator for lesson positions without kings, mini-boards (4×4–6×6), Pawn Wars, capture-all, King of the Hill and Chess960 castling |
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
the lesson in all three tracks, and validate every position (through `chess-core`): game positions must be fully legal; playground positions (for example a lone rook) are checked against the playground rules for that lesson.

## 7.5 Puzzles and content

- **Source:** the Lichess puzzle database (released under CC0, public domain): more than 4 million puzzles with ratings and theme tags (fork, pin, mateIn1 and so on). Filter and curate it for kids: short solutions, clear themes, no shocking positions.
- **Custom puzzles** for Levels 1–4 (movement, rule-discrimination puzzles) are authored in the lesson editor.
- **Hall of Legends:** public-domain historical games (PGN), annotated by the coaching team.
- Every puzzle has a concept tag that maps to the curriculum's concept list. This powers adaptive review.

## 7.6 Bots and engine

- Stockfish runs in a Web Worker so the UI never freezes. The default is a **single-threaded lite build**, loaded lazily the first time it's needed. Multi-threaded builds need SharedArrayBuffer, which requires cross-origin isolation headers (COOP/COEP); these are hard to guarantee inside Capacitor and are used only on the web build where the headers are set. Full-size NNUE networks (tens of MB) are an optional download for Academy analysis.
- Very weak bots (Bumble, Fizz, Rocky) use our own heuristics rather than Stockfish skill levels, which don't play convincingly human below about 800; they are tuned through play-tests.
- **Licence:** Stockfish is GPLv3. It is kept as a separate, replaceable component with its source published; see [document 15](15-business-legal-compliance.md) before shipping.
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
ChildProfile                      id, account_id (optional), avatar_id, age_band, track, settings
                                  (no name, no email, no photo; a certificate name is typed by a parent
                                  into the PDF on the device and never stored)
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
- No ads, no third-party trackers, no data selling. Analytics events carry a random profile ID, which is *pseudonymous*, not anonymous: under GDPR it is personal data and under COPPA it is a persistent identifier. It is covered by the privacy notice, the data-protection impact assessment (DPIA) and parental consent. Reports to staff are aggregated.
- The full privacy and compliance workstream (COPPA 2025 rule changes, GDPR age of consent by country, school privacy law, app-store kids rules) is in [document 15](15-business-legal-compliance.md).
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

## 7.11 Additions from critique round 2

### Storage that doesn't disappear
- Safari deletes website storage (including IndexedDB) after 7 days without use for sites not added to the home screen, and any browser can evict storage under pressure. A local-only profile could vanish.
- The web build calls `navigator.storage.persist()` and asks families to add the app to the home screen; the iOS and Android apps store progress in native storage (SQLite through Capacitor), not in WebView storage.
- After Level 1, a parent-gated **"Save my progress"** prompt offers to link the profile to a parent account (QR code or short code on the parent's phone). Profiles can also be exported and imported as a file.

### Sync and content versioning
- The same profile on two devices merges by rules per field: stars and badges keep the best value; mastery estimates replay the answer log in time order; spaced-repetition schedules take the most recent review.
- Lesson IDs and concept IDs never change between releases. When a lesson is rewritten, its ID keeps pointing at the same concept, and mastery data migrates with a versioned migration script.

### Realtime service (P2–P3)
Friend games, class tournaments and the projector quiz need a realtime layer: WebSocket channels (for example Supabase Realtime), presence, reconnection, server-side move validation (the server runs `chess-core`), clocks kept by the server, and basic fair-play checks.

### Observability
Crash and error reporting is self-hosted (for example a self-hosted Sentry instance) with personal-data scrubbing, because third-party SDKs are not allowed in kids-category apps. Product analytics use the first-party pipeline from 7.1, with an event list reviewed for privacy (no free text, no identifiers beyond a random profile ID).

### Speech
Voice answers use only speech recognition that runs on the device (for example Apple's on-device recognition in the iOS app, or a small bundled model). Browser speech APIs that send audio to a server are not used. The feature is off by default and parent-enabled.

### Devices supported
| Platform | Minimum | Notes |
|---|---|---|
| iPad / iPhone | iOS 16+ (WebGL2, WebAssembly SIMD) | App Store build via Capacitor |
| Android phones and tablets | Android 9+ with a current WebView | Google Play build |
| Amazon Fire tablets | Fire OS 7+ | Amazon Appstore build; no Google services |
| Chromebooks | ChromeOS current | Web app (PWA); "stream only" mode for small disks |
| Windows / macOS | Current Chrome, Edge, Safari, Firefox | Web app; keyboard play supported |
| Electronic boards (P3) | Bluetooth boards with open protocols | Real-board play with automatic move entry |

### Licences
A licence register lists every library, engine, model, font, sound, 3D model, HDRI and music track with its licence (for example chess.js: BSD-2; Stockfish: GPLv3; Lichess puzzle database: CC0; GSAP: its own no-charge licence, not open source). The app has an "Open-source licences and credits" screen. Details in [document 15](15-business-legal-compliance.md).
