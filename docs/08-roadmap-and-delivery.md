# 8. Roadmap & Delivery Plan

## 8.1 Phases

| Phase | Duration (estimate) | Scope | Exit criteria |
|---|---|---|---|
| **0. Discovery and prototype** | 4–6 weeks | Interviews with kids, parents and teachers; art style tests (3 piece-set styles); a playable R3F board prototype; Pip character test; tech spike (Stockfish WASM, Rive, Capacitor) | Art direction approved; kids aged 5–7 can move pieces unaided; 60 fps on mid-tier tablets |
| **1. MVP: "Learn the Rules"** | 14–16 weeks | Levels 0–3 (63 activities, 41 lessons), Little Knights and Explorers tracks, 16 mini-games, 3D board with 2 themes plus 2D mode, 3 friendly bots, offline mode, parent hub (basic), **voice assistant on every screen in English, Malayalam, Hindi and Arabic** | 90% of test kids pass a delayed rules re-test 30 days later; zero adult interventions for 90% of testers; D7 retention ≥ 35% in the beta, in every launch language |
| **2. "Play and Improve"** | 12–14 weeks | Levels 4–6, Academy track, Puzzle Gym (adaptive), game review, 6 bots, more themes, teacher mode v1 with class sign-in and rostering, parent web dashboard | Puzzle rating growth for 60% of active kids month-on-month; 20 pilot classrooms |
| **3. "Become a Master"** | 16–20 weeks | Levels 7–10, Repertoire Builder, Hall of Legends, tournament simulator, AR mode, friend games with invite codes, live AI coach (opt-in), more languages (for example Urdu, Tamil, Spanish, French) | Full curriculum live; app store launch; club and federation partnerships |
| **4. Live operations** | Ongoing | Weekly quests, seasonal kingdoms, new board themes, coach content, school programmes, competitions | Retention and learning KPIs met each quarter |

## 8.2 MVP feature list (Phase 1)

**Must have**
- [ ] Play-first onboarding with **no account and no reading**: tap the bell (sound check), tap the cake (age), pick an avatar, first piece touched within 30 seconds ([11.2](11-self-guided-learning.md#112-first-launch-with-no-adult-present)). A parent gate protects settings, sync and purchases
- [ ] Simple home screen: ▶ Continue + four doors (Learn, Practise, Play, My Trophies); ❓ Help, 🔁 Show me again and 🏠 Home on every screen
- [ ] Guide question rhythm (a question every 30–60 s), the 12 question types, 3 explanation styles per concept, and the escalation path
- [ ] Scenario playbook behaviours A–H from [11.7](11-self-guided-learning.md#117-scenario-playbook-what-the-app-does-when) (idle, random tapping, frustration, returning after a break and so on)
- [ ] Coached games: blunder warnings, check alerts, special-move hints, 3-moment review
- [ ] The Review Queue (spaced repetition)
- [ ] Rules coverage matrix check in CI (every rule has a lesson, practice, question and boss item)
- [ ] Adventure map: Board Village, Piece Valley, Royal Castle
- [ ] Lessons 0.1–3.18 in the Pip voice (LK and EX), recorded in English, Malayalam, Hindi and Arabic, with subtitles
- [ ] Voice assistant on every screen ([document 16](16-voice-assistant-and-languages.md)), language picker, right-to-left Arabic UI
- [ ] Simple placement quest (rules check) for any age; Review Islands; Real Board Challenge
- [ ] Persistent storage and the parent-gated "Save my progress" link
- [ ] Kids-category compliance (no third-party SDKs; parent PIN; consent) and the licence register ([document 15](15-business-legal-compliance.md))
- [ ] 3D board (Story Set + Adventure Set), tap and drag moves, legal dots, highlights, 2D toggle
- [ ] chess-core with every rule, including castling, en passant, promotion, and all draws
- [ ] Mini-games (16): Tap Hold Slide, Count & Colour, Wake the Pieces, Who's Who?, File & Rank Catch, Board Map Quiz, Build the Army, Coordinate Rush, Star Collector, Knight's Quest, King's Walk, Pawn Wars, Hungry Pieces, Mate or Stalemate?, Sneaky Check Spotter, Myth Buster
- [ ] Bots: Bumble, Fizz, Rocky
- [ ] Boss battles for Levels 1–3, certificates
- [ ] Stars, stickers, simple badges
- [ ] Offline mode + sync
- [ ] Parent hub: progress, time limits
- [ ] Privacy compliance (consent flow, no PII for children)

**Should have**
- [ ] Pass-and-play family mode
- [ ] Quality auto-detection

**Won't have in the MVP:** AR, friend games, AI coach, Academy track, Levels 4–10.

## 8.3 Team (Phase 1)

| Role | Count |
|---|---|
| Product manager | 1 |
| Learning designer (education background) | 1 |
| Chess coach / curriculum lead (FIDE trainer or titled player) | 1 (part-time OK) |
| Frontend / 3D engineers (React + Three.js) | 2–3 |
| Backend engineer | 1 |
| 3D artist (pieces, boards, environments) | 1–2 |
| 2D / Rive character animator | 1 |
| UX/UI designer (child UX experience) | 1 |
| Sound designer + voice-over casting in 4 languages (outsourced) | contract |
| Localisation lead + native-speaking chess reviewers (Malayalam, Hindi, Arabic) | 1 + part-time reviewers |
| Privacy and legal counsel (children's privacy, licences, trademarks) | part-time / external |
| QA engineer | 1 |
| Child UX researcher (play-tests) | part-time |

## 8.4 Workflow per lesson (content pipeline)

1. **Curriculum lead** defines the objective, positions and common misconceptions.
2. **Learning designer** writes the script in the format of [document 4](04-lesson-scripts.md) (Pip and Nova versions), then it is localised into Malayalam, Hindi and Arabic and reviewed by native-speaking chess coaches.
3. **Chess review:** every position is verified (lesson validator + a human coach).
4. **Voice-over recording** and localisation.
5. **Implementation** in the lesson editor (YAML), with animation hooks.
6. **Play-test** with 5+ kids in the target age band; iterate.
7. **Release** behind a feature flag; monitor completion and failure points.

## 8.5 KPIs and analytics

| Area | Metric | Target (after launch) |
|---|---|---|
| Learning | Rules re-test pass rate 30 days after Level 3 | ≥ 90% |
| Learning | Real-board transfer test (school pilots) | Rules applied correctly by ≥ 85% |
| Self-guided | Adult interventions in play-tests (Level 1, ages 5–6; Levels 1–3, age 8) | Zero for ≥ 90% of children |
| Learning | Concepts mastered per active child per week | ≥ 2 |
| Learning | Puzzle rating growth per month (active kids) | +50 or more |
| Engagement | D1 / D7 / D30 retention | 55% / 40% / 25% |
| Engagement | Lesson completion rate | ≥ 85% |
| Wellbeing | Average session length within the age target | ≥ 80% of sessions |
| Trust | Parent NPS | ≥ 50 |
| Schools | Active classrooms; assignment completion | Growth quarter on quarter; ≥ 70% |

## 8.6 Risks and mitigations

| Risk | Mitigation |
|---|---|
| 3D too heavy for school Chromebooks | Quality tiers, 2D fallback, streamed asset packs, early device lab |
| Young kids can't use drag gestures | Tap-tap moves, big targets, errorless mode, early play-tests |
| Content volume (about 180 lessons × 2 guide voices + supporting cast × 4 languages) | Data-driven lessons, lesson editor, reusable mini-game generators, phased release |
| Teaching errors in rules | This rules reference as the single source of truth; automated validation; coach review |
| Kids get bored after learning the rules | Bots with personality, quests, Pawn Wars and other variants, family play, seasonal events |
| Privacy or compliance issues | Privacy by design, legal review before launch, no PII, no chat |
| Monetisation pressure leading to dark patterns | Business model: freemium for families (Levels 0–3 free; subscription for the full academy) + school licences; no ads, no loot boxes. Full spec in [document 15](15-business-legal-compliance.md) |
| Product name conflicts with an existing trademark ("Chessmaster" is a long-running chess video-game brand) | Trademark clearance before any branding work; choose a new name if needed (see document 15) |
| Stockfish's GPLv3 licence and app-store terms | Legal opinion before release; engine as a separate, replaceable component with source published |
| Kids-category app-store rejection | Compliance checklist and SDK allow-list from day one (document 15) |
| Progress lost through browser storage eviction | Persistent storage, native storage in apps, "Save my progress" link |
| Voice quality in Malayalam, Hindi and Arabic | Native-speaking chess reviewers, child play-tests per language, per-language AI evaluation |

## 8.7 Immediate next steps

1. Approve this plan and the art direction options.
2. Hire or assign the curriculum lead and learning designer; finalise the Level 1–3 scripts.
3. Build the Phase 0 prototype: 3D board + Pip + lessons 2.1 (Rook) and 2.9 (Knight) end to end.
4. Run play-tests with 10 kids (ages 5–7 and 8–10) and refine.
5. Set up the repository structure from [7.9](07-technical-architecture.md#79-repository-layout-proposed), with CI running the perft and lesson-validation tests.
