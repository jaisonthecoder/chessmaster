# 5. Teaching Method & Engagement

## 5.1 Teaching techniques built into the app

| Technique | What it means | Where it shows up in the app |
|---|---|---|
| **Scaffolding: I do, we do, you do** | Demonstrate, then guide, then let the child work independently | The Watch → Try → Practise structure of every lesson |
| **Concrete → pictorial → abstract** | Physical, then visual, then symbolic | 3D characters → 2D diagrams → algebraic notation (by track) |
| **One concept per lesson (chunking)** | Small, digestible units reduce cognitive load | 3–7 minute lessons; the board is cleared of irrelevant pieces |
| **Reduced boards** | Teach a piece with only that piece on the board | All of Level 2 uses sparse boards and mini-boards |
| **Mastery learning** | Move on only when ≥ 80% correct | Lesson checks and Boss gates |
| **Retrieval practice** | Recalling builds memory better than re-reading | Every lesson starts with a 30-second "Remember?" question from an earlier lesson |
| **Spaced repetition** | Review at growing intervals | Concept mastery scores decay; the Review Queue and puzzle scheduling use an SM-2-like algorithm |
| **Interleaving** | Mixing problem types improves discrimination | Mixed puzzle sets after Level 5 ("Which tactic is it?") |
| **Immediate, specific feedback** | Explain *why* it's right or wrong | Every wrong move gets a contextual reason ("That square is attacked by the bishop") |
| **Errorless learning (ages 5–7)** | Prevent failure spirals in young children | Illegal moves bounce back gently, with the hint ladder |
| **Hint ladder** | Least help first | Nudge → highlight → legal dots → ghost-hand demo |
| **Storytelling and characters** | Narrative improves memory and motivation | Pip's journey from pawn to queen; a kingdom per level |
| **Mnemonics** | Memory hooks | "Light on the right", "Queen on her colour", "Run-Capture-Block", "a knight on the rim is dim" |
| **Multisensory learning** | Visual, auditory and kinaesthetic | 3D motion, voice, sound effects, drag gestures, AR board, printable worksheets for the table |
| **Worked examples** | Study solved examples before solving | Academy "Model Game" walk-throughs; Hall of Legends |
| **Deliberate practice** | Targeted practice just beyond the current level | The adaptive engine targets ~75% success on puzzles |
| **Metacognition** | Thinking about one's own thinking | "Safety Check" routine (checks, captures, threats); Academy "Why did you choose that move?" reflections |
| **Learning from mistakes** | Turn errors into lessons | "Oops Replays": the child's own blunders become personal puzzles |
| **Growth-mindset feedback** | Praise effort and strategy, not talent | "You kept looking for the checks, and found it!" rather than "You're so smart" |
| **Peer and family learning** | Social reinforcement | Pass-and-play family mode with "Teach your parent" quests |

## 5.2 The "Safety Check" thinking routine

Taught in Level 4 and reinforced forever. A small shield icon appears before each move in practice games.

1. **What did my opponent's last move do?** (new threats?)
2. **Checks, captures, threats:** for both sides.
3. **Is my piece safe on its new square?**

For Little Knights it is simplified to: *"Is anything in danger? Is my piece safe?"*

## 5.3 Adaptive learning engine

- **Child model:** a skill rating per concept (Glicko-2-style rating with uncertainty) plus an overall puzzle rating.
- **Puzzle selection:** choose puzzles near the child's rating, tagged with the concepts due for review. Aim for 70–80% success.
- **Frustration detection:** 3 failures in a row, rapid random taps, or long idle time lowers the difficulty, offers a hint, or suggests a fun mini-game break.
- **Boredom detection:** very fast perfect streaks unlock "Challenge mode" or skip ahead (with a quick placement check).
- **Session pacing by age:** a soft break reminder at 15 minutes (5–7), 25 minutes (8–10) and 45 minutes (11–15). Parents can configure daily limits.

## 5.4 Motivation design

Based on **Self-Determination Theory**: autonomy, competence and relatedness.

| Need | Feature |
|---|---|
| **Competence** | Visible progress (map, stars, levels), Boss victories, rating graphs (Academy) |
| **Autonomy** | Choose the next lesson from several unlocked ones, choose a bot opponent, customise the board and pieces, choose an opening repertoire |
| **Relatedness** | Characters who "remember" the child, family games, class challenges, safe friend matches |

### Gamification elements
- **Stars (1–3)** per lesson and mini-game, so a lesson can be replayed for a better score.
- **XP and levels** for Explorers and Academy.
- **Badges:** concept badges (Fork Master I–III), behaviour badges (Practised 5 days, Used the Safety Check 50 times).
- **Collectibles:** board themes (Enchanted Forest, Ocean Reef, Space Station, Candy Land, Desert Dunes, Classic Tournament Walnut), piece sets, Pip outfits. All are **earned, never bought with real money**.
- **Gentle streaks:** "Practice days this week" (not consecutive-day pressure), with free "rest days".
- **Daily Puzzle** and **Weekly Quest** (for example, "Win 3 games by castling early").
- **Leaderboards:** friends and class only. Never global for under-13s.

### What we deliberately avoid
- Loot boxes, gacha, paid currency, ads, countdown timers that push purchases.
- Guilt-based notifications ("Pip is sad you left").
- Public rankings for young children; open chat.

## 5.5 Family and classroom

### Parent hub
- Weekly progress report: concepts mastered, time spent, highlight replays.
- Screen-time limits and quiet hours.
- "Play with your child" suggestions and printable activity sheets.
- Certificates (PDF) at each level.

### Teacher and coach mode
- Create a class with join codes (no student email needed).
- Assign lessons, puzzle sets and bot games; set due dates.
- Class heat-map: students × concepts (green, amber, red).
- **Projector mode:** a large 3D board, teacher-controlled demonstrations, "everyone answer on your tablet" quiz mode.
- Tournament organiser: in-class Swiss or round-robin tournaments.
- Lesson plans that align with the app's levels (a downloadable PDF per lesson).

## 5.6 Inclusion

- Gender-balanced characters and Hall of Legends stories (for example, Vera Menchik, the Polgár sisters, Hou Yifan, Ju Wenjun).
- Culturally diverse board themes and stories, including chess history from India (chaturanga), Persia (shatranj) and the Arab world (the history of shatranj, and the Arabian Mate pattern).
- Support for neurodivergent learners: predictable lesson structure, a calm mode (reduced effects and sound), adjustable pacing.
