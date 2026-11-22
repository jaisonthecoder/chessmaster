# 14. Critique Round 2: Full Inspection and Fixes

**Method:** an independent reviewer read all documents (README and 01–13) without seeing our own list of suspected
problems, checked every lesson-script position square by square, and reported 121 findings in 7 categories. A separate
mechanical check counted lessons, mini-games and scenarios and verified cross-links. Each finding was checked against
the documents before it was accepted. The user then added a new requirement (a voice assistant on every screen in
English, Malayalam, Hindi and Arabic), handled in [document 16](16-voice-assistant-and-languages.md).

## 14.1 Before and after

| Measure | Before round 2 | After round 2 |
|---|---|---|
| Levels | 10 | 11 (new Level 0, Pip's Playroom, for ages 5–6) |
| Activities in the curriculum | 118 | 214 |
| Lessons (🎬) | 92 (claimed "about 120") | 177 |
| Mini-games | 21 (claimed "more than 30") | 37, with rule specs for the core games |
| Scenario playbook | 55 (claimed "40+" and "60+") | 69 |
| Screens | 74 | 101 |
| Launch languages | English (Arabic in phase 2) | English, Malayalam, Hindi, Arabic, with a voice assistant on every screen |
| Documents | 13 | 16 |

## 14.2 Top 10 problems fixed first

| # | Problem | Fix | Where |
|---|---|---|---|
| 1 | Children had to *win* games at Level 4 but learned basic checkmates only at Level 6 | Two-rook, queen + rook and queen + king mates moved into Level 4 (4.10–4.12) | 03 |
| 2 | The name "ChessMaster" conflicts with an existing chess video-game brand | Trademark clearance before branding; working title only | 15.1 |
| 3 | Stockfish is GPLv3; app-store and licence risks | Legal opinion; engine as a separate, replaceable component; licence register | 15.2, 07 |
| 4 | Children's privacy gaps (COPPA 2025 changes, GDPR, India's DPDP Act, school law) and "anonymous" analytics that are really pseudonymous | Full privacy workstream; analytics described correctly | 15.3, 15.5, 07 |
| 5 | chess.js can't load lesson positions without kings, mini-boards or variants | `chess-core` playground layer | 07 |
| 6 | Browser storage can be wiped (Safari after 7 days), losing local-only progress | Persistent storage, native storage, "Save my progress" link | 07.11, 11 |
| 7 | "Two voice sets" contradicted scripts with many speaking characters | Two guide voices + a shared supporting cast per language; realistic line count | 04, 06, 16 |
| 8 | An 80% gate on 3 questions needs 3/3, and yes/no questions can be guessed | At least 5 items, at least 2 types, 4 of 5 to pass, delayed re-check | 03, 04 |
| 9 | Real-board skills only at Level 10; legal-move dots never fade | Playing on a Real Board (3.16), Real Board Challenge, Tournament Mode (4.21), dot fading | 03, 05 |
| 10 | No kids-category app-store plan | Compliance checklist, SDK allow-list, no push notifications in the child app | 15.4 |

## 14.3 Chess content added

| Level | Added |
|---|---|
| **0 (new)** | Tap/Hold/Slide, directions incl. diagonal, counting to 8, light and dark, picture letters, taking turns, winning/losing/ties are OK |
| **1** | Your Real Chessboard at Home; Where Chess Came From (chaturanga, shatranj, modern rules) |
| **2** | Who Guards Whom? (protection); Strong in the Middle (mobility). Map lands reordered to match the teaching order |
| **3** | Sneaky Checks; How a Game Ends; draw *claims*; Chess Myths Busted!; Playing on a Real Board; Real Board Challenge |
| **4** | Count Attackers and Defenders; Five Ways to Save a Piece; Stop the Mate Threat!; basic mates; The Weakest Square f7 (Fool's and Scholar's Mate); phases of the game; trading when ahead; notation; Clock 101; Tournament Mode |
| **5** | How to Solve a Puzzle; royal vs family forks; double check; deflection; decoy; overloading; interference; clearance; x-ray; zwischenzug; desperado; trapped pieces; promotion tactics; perpetual check and stalemate tricks; corridor mate; three mating-pattern lessons (about 16 named mates); windmill; Which Tactic Is It?; Visualisation Flash |
| **6** | Rook-pawn and wrong-bishop draws; distant opposition and shouldering; triangulation; outside passed pawn; protected and connected passers; underpromotion; queen vs pawn; rook vs pawn; rook behind the passed pawn; Lucena and Philidor split; knight and bishop endgames; opposite-coloured bishops; fortress; optional B+B, B+N and Q vs R mates; Endgame Trainer |
| **7** | Out of Book?; Two Knights Defence; Scotch, Four Knights, Petrov; Caro-Kann; meeting 1.d4 as Black; English and Réti; a second traps lesson (7 more traps); transpositions; from opening to plan |
| **8** | Centralisation; space; weak squares; IQP; hanging pawns; majorities and the minority attack; rook lifts; colour complexes; opposite-side castling; initiative; static vs dynamic; overprotection; exchange sacrifice; two weaknesses; converting an advantage; defending worse positions |
| **9** | Blunder check; calculation tree; evaluating the final position; when to stop calculating; typical sacrifices; defensive resources |
| **10** | Scoresheet rules; simple vs Bronstein delay; time scrambles; calling the arbiter; draw offers and claims procedure; rapid and blitz differences; phones and fair play; your first tournament day; Swiss pairings and tiebreaks; preparing for an opponent; win vs draw decisions; online chess safely and fairly; FIDE ID; Chess960 |
| **After 10** | Training Plan mode with honest time estimates; Review Islands between kingdoms |

## 14.4 Chess accuracy fixes

| Finding | Fix |
|---|---|
| Stalemate described as "nobody can move" | Only the side to move has no legal move (02, 11) |
| Knight's "flower" described wrongly | The targets lie on the edge of a 5×5 box, never its corners or side middles (02) |
| Bronstein and simple delay treated as one thing | Described separately (02) |
| Outdated rating floor and title facts | FIDE floor of 1400 since 2024; norms for women's titles; GM norms over at least 27 games; yearly re-check (02) |
| Dead positions listed only as material | Blocked-pawn dead positions added, with an engine note (02, 07) |
| Threefold repetition definition | "Same possible moves"; en passant only if legal (02) |
| Automatic draws for young children (not real chess) | Every track claims draws with the guide's prompt; fivefold and 75-move are automatic (02, 11) |
| Timeout and second-illegal-move edge cases missing | Added to the rules and the QA list (02) |
| Castling notation and PGN letters | 0-0 on FIDE scoresheets, O-O in PGN; PGN always English letters (02) |
| Lesson 2.11: knight placed on an occupied square | Knight moved to f4 (04) |
| Lesson 5.2: fork position under-specified | Full FEN given and verified (04) |
| Lesson 3.2: "several blocking squares" with only one possible | Knight c3 and bishop f1 added (04) |
| Ambiguous check questions | Reworded (04) |
| Rating scale unclear | Lichess rapid scale named, with caveats (03) |
| Snapping could make unintended moves in games | Snapping in lessons only (11) |

## 14.5 Self-guided learning fixes

Language picker before anything else; a two-step age picker with a grown-up button; asking "did you hear the bell?"
instead of claiming to detect mute; placement and "Prove it!" for any age; parent PIN for limits and purchases;
14 new scenarios (repeated boss failure, plateaus, bot reactions, accidental resign, background during a boss,
reinstall, clock tampering, wrong avatar, referee mode, house rules, always-White, and accessibility for deaf, blind
and motor-impaired children); the Pip-to-Nova hand-over; adapted advanced content for strong young children;
a "why?" question after every teach-back; one mastery model; the "Remember?" step in every lesson; a story arc for
every kingdom; a separate home and motivation design for teenagers.

## 14.6 Product, technical and business additions

- **Screens (27 new):** language picker, parent setup, Academy home, Review Island, Training Plan, Real Board Challenge, Endgame Trainer, referee mode, game history, rated games for 13+, quests, leaderboards, friends, language and voice settings, unlock, save progress, parent login, restore purchases and codes, help centre, legal and credits, downloads manager, delete account, parent web dashboard, class sign-in, rostering and SSO, projector live session, teacher verification.
- **Technical:** playground rules layer; persistent and native storage; lite engine by default with cross-origin-isolation notes; realtime service; sync and content versioning; self-hosted crash reporting; first-party analytics; on-device speech only; device support matrix (including Amazon Fire); phone camera and touch-target fix; iOS AR re-scoped; WebGL recovery; storage budget; battery saver.
- **AI:** structured claims checked by the engine; correct caching economics; latency benchmark including Claude Haiku 5.5; one under-13 policy for all live AI; "written by AI" label; usage-policy review; per-language AI evaluation.
- **Business and legal:** document 15 (name, licences, privacy, app stores, schools, online safety, voices, advertising, business model, launch checklist).
- **Bots:** guide characters are never opponents (bots renamed); bot draw-acceptance rules.

## 14.7 Still open (decisions for the team)

1. Final product name after trademark clearance.
2. Whether to keep Stockfish (GPL) or adopt an engine with a permissive licence, after the legal opinion.
3. Exact prices per market and the number of profiles per family plan.
4. Malayalam, Hindi and Arabic chess terms marked "confirm" in document 16.
5. Whether Gulf-dialect Arabic voices are added after the Modern Standard Arabic launch.
6. When rated games against other players (13+) launch, after the UK Online Safety Act risk assessment.
