# 12. Features & Screens Inventory

Every screen and feature in the plan (documents 1–16). Every child screen has the voice assistant described in [document 16](16-voice-assistant-and-languages.md), grouped by app area.
**Phase:** P1 = MVP, P2 = "Play and Improve", P3 = "Become a Master" (see [Roadmap](08-roadmap-and-delivery.md)).

## 12.1 Sitemap

```
App launch
├── A. First launch (no account)
│     Sleeping board → Sound check → Age cakes → Pick avatar → (8+) "Do you know chess?" → Placement quest / Lesson 1.1
├── Who's playing? (avatar faces)
└── B. HOME  [ ▶ Continue ]   ❓ Help · 🔁 Show me again · 🏠 Home · 👤 Grown-ups corner
      ├── 📖 C. LEARN       Adventure Map → Kingdom → Lesson / Boss / Certificate
      ├── 🧩 D. PRACTISE    Mini-games · Puzzle Gym · Daily Puzzle · Oops Replays · Trainers
      ├── ♟ E. PLAY        Bots · Family · Friends · Variants · Tournament · Analysis · AR
      └── 🏆 F. MY TROPHIES Badges · Certificates · Collection · Progress · Hall of Legends
      
      G. System overlays (help, breaks, parent gate, downloads…)
      ── Parent gate ──▶ H. PARENT HUB
                        I. TEACHER / COACH MODE (separate login, web)
      J. Internal tools (lesson editor, admin)
```

## 12.2 Screens

### A. First launch and profiles
| # | Screen | What it does | Phase |
|---|---|---|---|
| A0 | Language picker | Device language preselected; flag-and-face buttons for English, Malayalam, Hindi and Arabic, each speaking its own language | P1 |
| A1 | Welcome (sleeping board) | Opens straight into the 3D world; no account, no text | P1 |
| A2 | Sound check | "Tap the bell!" Detects muted sound and switches on subtitles and icons | P1 |
| A3 | Age picker | Cakes with 5–15 candles, each spoken aloud; sets the guide (Pip or Coach Nova) | P1 |
| A4 | Avatar picker | 8 cartoon faces; no names or photos | P1 |
| A5 | "Do you know chess?" (8+) | 👍 / 🤔 / 👎, which routes to the placement quest or Level 1 | P1 |
| A6 | Placement quest | Any age, voice-led; 3 minutes, 12 adaptive 3D questions. P1 checks the rules (places up to Level 4); P2 extends it to Level 5 | P1 / P2 |
| A7 | Who's playing? | Avatar faces for children sharing one device; "Add a friend" | P1 |
| A8 | Parent setup and consent | From "I'm a grown-up": parent PIN, verifiable parental consent, optional account | P1 |

### B. Home
| # | Screen | What it does | Phase |
|---|---|---|---|
| B1 | Home | Pip, one big **▶ Continue** button, four doors (Learn, Practise, Play, My Trophies), "Today's adventure" progress ring | P1 |
| B2 | Always-present helpers | ❓ Help (explains a different way), 🔁 Show me again, 🏠 Home (auto-saves) on every screen | P1 |
| B3 | Grown-ups corner icon | Opens the parent gate | P1 |
| B4 | Academy home (11–15) | Training dashboard: rating graph, today's plan, streaks, weak spots | P2 |

### C. Learn
| # | Screen | What it does | Phase |
|---|---|---|---|
| C1 | Adventure Map | 3D world of 10 kingdoms; locked kingdoms show when they open | P1 (L1–3), P2 (L4–6), P3 (L7–10) |
| C2 | Kingdom view | Lesson stops, mini-games and the boss gate. In Piece Valley the child travels by the piece's own movement | P1 |
| C3 | Lesson player | 3D scene + guide character + interactions; a question every 30–60 s; hint ladder; 3 explanation styles; subtitles (8+) | P1 |
| C4 | "Remember?" warm-up | 1–5 spaced-review questions at the start of a session | P1 |
| C5 | "Too easy? Prove it!" ⚡ | Test out of a lesson with its check questions (8+) | P1 |
| C6 | Lesson complete | Stars (1–3), sticker or badge, map step forward, "Next time…" teaser | P1 |
| C7 | Boss Battle | 3 rounds (recall, apply, play), hearts (unlimited for 5–7) | P1 |
| C8 | Practice Camp | After a failed boss: 2 targeted activities, then retry | P1 |
| C9 | Level certificate | On-screen certificate, "Show a grown-up!" button | P1 |
| C10 | Review Island | Mixed review of all earlier levels before the next kingdom opens | P1 |
| C11 | Training Plan | Weekly rating-based plan after Level 10 (from Level 7 by choice) | P3 |

### D. Practise
| # | Screen | What it does | Phase |
|---|---|---|---|
| D1 | Practise hub | Cards for mini-games, puzzles, my mistakes and trainers | P1 |
| D2 | Mini-games library | Unlocked games with best stars | P1 |
| D3 | Mini-games (each its own screen) | Wake the Pieces, Who's Who?, File & Rank Catch, Board Map Quiz, Build the Army, Coordinate Rush, Star Collector, Knight's Quest, King's Walk, Pawn Wars, Hungry Pieces, Mate or Stalemate? | P1 |
| D4 | More mini-games | Safe Square, Guard the Treasure, Fork Finder, Puzzle Dash Jr., Mini-Board Battles, King of the Hill | P2 |
| D5 | Puzzle Gym | Adaptive puzzles (about 75% success target) and themed sets (forks, pins, mates…) | P2 |
| D6 | Daily Puzzle | One puzzle a day, matched to the child | P2 |
| D7 | Oops Replays | The child's own mistakes from games, turned into puzzles | P2 |
| D8 | Review Queue | Concepts due for spaced review | P1 |
| D9 | Trainers | Coordinate trainer (P1); Memory Board and Blind Knight visualisation (P3) | P1 / P3 |
| D10 | Repertoire Builder | Spaced-repetition training of the child's opening lines (Level 7) | P3 |
| D11 | Real Board Challenge | Set up the shown position on a real board, play the answer there, confirm in the app | P1 |
| D12 | Endgame Trainer | Convert or hold key endgame positions against the engine | P2 |

### E. Play
| # | Screen | What it does | Phase |
|---|---|---|---|
| E1 | Play hub | Choose: computer, family, friend, variants, tournament | P1 |
| E2 | Bot picker | Character cards (Bumble, Fizz, Rocky → Sir Clank, Luna, Captain Rook, Coach Nova, Shadow) | P1 (3 bots), P2 (6+) |
| E3 | Game setup | Colour, coaching level, variant; clock and time control (older kids) | P1 |
| E4 | Game screen | 3D board, coach voice, captured-pieces tray, legal-move dots, last-move highlight, 2D/3D toggle, flip board, hint, save for later, resign, offer draw, take-back (practice only) | P1 |
| E5 | Promotion picker | 4 big icons (Queen, Rook, Bishop, Knight) | P1 |
| E6 | Game over | Win, loss or draw, with the reason explained; rematch, easier or harder bot | P1 |
| E7 | Coach's Corner review | 3 key moments at most, each asked as a question | P2 |
| E8 | Pass-and-play | Family game on one device; the board turns; the coach explains to both | P1 (should have) |
| E9 | Variants | Pawn Wars, mini-boards, King of the Hill, Chess960 | P1 (Pawn Wars, mini-boards), P3 (Chess960) |
| E10 | Friend games | Invite codes plus parent approval; preset emotes only, no chat | P3 |
| E11 | Tournament simulator | 5-round Swiss against bots with clock and scoresheet (Level 10) | P3 |
| E12 | Analysis board | Free board, arrows, engine (Academy), PGN export | P3 |
| E13 | AR board | Place a 3D board on a real table; Pip teaches on it; "shadow board" mode | P3 |
| E14 | Referee mode | Helps with a game on a real board: enter moves, legality help, chess clock | P2 |
| E15 | My games | History of the child's games, replay, export (PGN for Academy) | P1 |
| E16 | Rated games (13+) | Opt-in, parent-approved games against other players aged 13+, no chat | P3 |

### F. My Trophies
| # | Screen | What it does | Phase |
|---|---|---|---|
| F1 | Trophy room | Stars, badges, stickers, certificates | P1 |
| F2 | Collection / customise | Board themes, piece sets, Pip outfits, avatar (all earned, never bought) | P1 (2 themes), P2+ |
| F3 | My progress (child view) | Map progress, "days played this week"; ratings for Academy | P1 |
| F4 | Hall of Legends | Stories of great players with their famous moments as puzzles | P3 |
| F5 | Quests | Daily and weekly quests | P2 |
| F6 | Leaderboards | Friends and class only | P2 |
| F7 | Friends | Friends added through invite codes and parent approval | P3 |

### G. System overlays
| # | Screen | What it does | Phase |
|---|---|---|---|
| G1 | Help overlay | The guide explains in the next explanation style | P1 |
| G2 | Idle and sleep | Re-prompt, re-explain, then Pip "falls asleep" and progress is saved | P1 |
| G3 | Slow-down breathing | After random tapping: a 5-second breathing animation, then an easier item | P1 |
| G4 | Break reminder / time's up | Gentle break by age; parent time limit applied at a natural stopping point | P1 |
| G5 | Parent gate | Adult-only check before settings, purchases and links | P1 |
| G6 | "Ask a grown-up" | Friendly message when a child hits a gated action | P1 |
| G7 | Downloading kingdom | Streams the next asset pack; works offline afterwards | P1 |
| G8 | Welcome back | Returning-child greeting + warm-up | P1 |
| G9 | What's new | Pip shows new things, only when relevant | P2 |
| G10 | Quick settings (child) | Sound, music, 2D/3D | P1 |
| G11 | Language and voice | Change language (per profile), voice speed, subtitles | P1 |
| G12 | Unlock ("ask a grown-up") | Shown when content needs a subscription; never interrupts a lesson | P2 |
| G13 | Save my progress | Parent-gated prompt to link the profile to a parent account (QR or code) | P1 |

### H. Parent hub (behind the parent gate)
| # | Screen | What it does | Phase |
|---|---|---|---|
| H1 | Parent dashboard | Concepts mastered, time spent, highlights, current level | P1 |
| H2 | Account and cloud sync | Optional account, parental consent, sync across devices | P1 |
| H3 | Child profiles | Add or remove profiles, change the age track | P1 |
| H4 | Screen time | Daily limits, quiet hours | P1 |
| H5 | Settings | Language; accessibility (colour-blind palette, reduced motion, calm mode, dyslexia font, text size, subtitles, left-handed); graphics quality; voice answers (P3); AI coach (P3); friend approval (P3) | P1+ |
| H6 | Reports and certificates | Weekly report email, certificate PDFs, printable activity sheets, "play with your child" ideas | P2 |
| H7 | Subscription | Free Levels 1–3; full academy subscription | P2 |
| H8 | Privacy | Export and delete data | P1 |
| H9 | Parent login and password reset | Email or social sign-in for parents | P1 |
| H10 | Restore purchases and redeem codes | Required by the app stores; school and gift codes | P2 |
| H11 | Help centre and support | FAQ, contact support, report a problem | P1 |
| H12 | Legal and credits | Privacy policy, terms, open-source licences and credits | P1 |
| H13 | Downloads and storage | Download or remove kingdoms and languages; storage used | P1 |
| H14 | Delete account | Confirmation and what will be deleted | P1 |
| H15 | Parent web dashboard and email digest | The parent hub on the web and phone, with a weekly email | P2 |

### I. Teacher / coach mode
| # | Screen | What it does | Phase |
|---|---|---|---|
| I1 | Teacher dashboard | Classes overview | P2 |
| I2 | Class management | Create classes, join codes (no student emails) | P2 |
| I3 | Assignments | Assign lessons, puzzle sets and bot games, with due dates | P2 |
| I4 | Class heat-map | Students × concepts (green, amber, red) | P2 |
| I5 | Projector mode | Large 3D board for demonstrations, whole-class quiz on tablets | P2 |
| I6 | Class tournaments | Swiss or round-robin in class | P3 |
| I7 | Lesson plans | Downloadable PDF per lesson | P2 |
| I8 | Class sign-in | Picture passwords or QR badges for shared classroom devices | P2 |
| I9 | Rostering and single sign-on | Google, Microsoft, Clever, ClassLink and OneRoster | P2 |
| I10 | Projector live session | Join code, anonymised names, live answers and results | P2 |
| I11 | Teacher verification | Confirms teacher accounts before class features unlock | P2 |

### J. Internal tools
| # | Screen | What it does | Phase |
|---|---|---|---|
| J1 | Lesson editor | Set up positions on a 3D board, write steps, preview in each track, validate legality | P1 |
| J2 | Admin console | Content, puzzles, users, feature flags | P1 |
| J3 | Analytics dashboard | Privacy-first learning and engagement metrics | P1 |

## 12.3 Behind-the-scenes features (no screen of their own)

| Feature | What it does | Phase |
|---|---|---|
| Rules engine | All FIDE rules, including castling, en passant, promotion and every draw; tested against the edge-case list | P1 |
| 3D board engine | Real-board feel (PBR wood, soft shadows, physical motion), themes, quality tiers, automatic 2D fallback | P1 |
| Bot engine | Stockfish with human-like personalities and mistakes | P1 |
| Coached-game engine | Blunder warnings, check alerts, special-move hints, take-backs | P1 |
| Adaptive engine | Concept mastery, spaced repetition, difficulty both up and down, frustration and boredom detection | P1 |
| Explanation rotation | 3 explanation styles per concept, escalation path, "always end on a success" | P1 |
| Scenario playbook | 60+ situation handlers (idle, random tapping, losing streak, returning after weeks…) | P1 |
| Voice and audio | Two voice sets (Pip, Nova), subtitles, music, wooden sound effects | P1 |
| Voice assistant on every screen | Entry line, 🔊 say it again, long-press to hear, help, idle prompts, optional on-device voice commands; read-aloud for parent and teacher pages. See [document 16](16-voice-assistant-and-languages.md) | P1 |
| Languages | English, Malayalam, Hindi and Arabic (right-to-left) at launch; more later | P1 |
| Offline mode | Downloaded kingdoms work without internet; sync later | P1 |
| Safety | No ads, no chat, no personal data, parent gate | P1 |
| Rules coverage check | The build fails if any rule lacks a lesson, practice, question and boss item | P1 |
| AI coach | Template → library → cache → live answer path; live explanations of the child's own games (P2); Ask Pip/Nova and teach-back grading (P3, opt-in). See [AI Strategy](13-ai-strategy.md) | P2 / P3 |
| Offline AI content factory | Batch-generated, human-reviewed explanation library, question banks, script and translation drafts | P1 |
