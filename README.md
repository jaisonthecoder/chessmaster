# ChessMaster Academy — 3D Chess Tutor for Kids (Ages 5–15)

ChessMaster Academy is an interactive, highly visual 3D chess learning application that takes a child
from *"what is a chessboard?"* all the way to tournament-ready play — and sets them on the path toward
becoming a titled chess master.

> **Core idea:** *Age sets the voice; skill sets the content.*
> A 6-year-old and a 14-year-old can both be learning how the knight moves — but the 6-year-old gets
> a story, a talking character and a game of "collect the stars", while the 14-year-old gets a crisp
> explanation, a timed drill and a rated puzzle streak.

## Planning documents

| # | Document | What it covers |
|---|----------|----------------|
| 1 | [Product Vision](docs/01-product-vision.md) | Goals, audiences, age tracks, design principles, safety, success metrics |
| 2 | [Chess Rules Reference](docs/02-chess-rules-reference.md) | Complete rules of chess (based on the FIDE Laws of Chess), with kid-friendly explanations, teaching notes and rules-engine edge cases |
| 3 | [Curriculum & Levels](docs/03-curriculum-and-levels.md) | The 10-level learning path, worlds map, every lesson, mini-game and "boss battle" |
| 4 | [Lesson Scripts](docs/04-lesson-scripts.md) | Screenplay-style scripts: what the character says, what the 3D scene does, what the child does, feedback on right and wrong answers |
| 5 | [Teaching Method & Engagement](docs/05-teaching-method-and-engagement.md) | Teaching techniques, adaptive learning, gamification, parent and teacher tools |
| 6 | [3D Visual, Audio & Interaction Design](docs/06-3d-visual-audio-design.md) | Art direction, the real-board feel, camera, animation, sound, accessibility |
| 7 | [Technical Architecture](docs/07-technical-architecture.md) | Technology stack, 3D rendering, chess engine, lesson scripting format, data, privacy |
| 8 | [Roadmap & Delivery Plan](docs/08-roadmap-and-delivery.md) | Phases, MVP scope, team, testing with kids, KPIs, risks |
| 9 | [Competitor Analysis](docs/09-competitor-analysis.md) | ChessKid, Dr. Wolf, Duolingo Chess, DragonBox (Magnus' Kingdom), Story Time Chess, Fritz & Chesster, Dinosaur Chess, Lichess and others: what works, what doesn't, and what we adopt |
| 10 | [Plan Critique, Round 1](docs/10-plan-critique.md) | Honest review of documents 1–8 and the changes made |
| 11 | [Self-Guided Learning](docs/11-self-guided-learning.md) | How a child learns completely alone: first launch with no adult, simple UI rules, a guide that asks questions, 12 question types, a playbook of 60+ scenarios, and a rules coverage matrix |
| 12 | [Features & Screens Inventory](docs/12-features-and-screens.md) | Every screen and feature, grouped by app area, with its release phase |
| 13 | [AI Strategy](docs/13-ai-strategy.md) | Where AI is used (engines, offline content generation, live coach), how to keep it cheap and fast, and child-safety rules |

## At a glance

- **Learns alone:** no adult needed. The app opens straight into play (no account), speaks every instruction,
  asks the child a question every 30–60 seconds, and explains things a different way when the child is stuck.
  One big **▶ Continue** button always leads to the right next step.
- **Audience:** children aged 5–15, plus their parents, teachers and chess coaches.
- **Three presentation tracks:** *Little Knights* (5–7), *Explorers* (8–10), *Academy* (11–15).
- **Ten skill levels:** Board Explorer → Piece Master → Royal Rules → First Games → Tactics Cadet →
  Endgame Builder → Opening Navigator → Strategist → Combination Master → Tournament Player.
- **About 120 lessons, more than 30 mini-games, and more than 5,000 adaptive puzzles at launch of the full curriculum.**
- **3D:** a real-board feel (wood, marble, soft shadows, physical piece motion), with a one-tap switch to
  a 2D top-down view and an optional augmented-reality (AR) board on the kitchen table.
- **Recommended stack:** TypeScript + React Three Fiber (Three.js) + chess.js + Stockfish (WebAssembly),
  packaged as a web app (PWA) and as iOS/Android apps through Capacitor.
