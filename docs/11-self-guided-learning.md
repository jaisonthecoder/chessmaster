# 11. Self-Guided Learning: The App Is the Teacher

**Requirement:** a child aged 5–15 must be able to learn chess **completely alone**. No parent, teacher or
older sibling is needed to start the app, read instructions, explain a rule, rescue them when stuck or
keep them motivated. The app must **guide, teach, question and adapt** like a patient human coach sitting
beside them.

**How we measure it:** in play-tests, an observer counts *adult interventions* (any time an adult has to help).
Target: **zero interventions** for 90% of 5–6-year-olds completing Level 1, and for 90% of 8-year-olds completing Levels 1–3.

---

## 11.1 The five promises to the child

1. **"I'll always tell you what to do next."** There is never a screen without a spoken instruction and one obvious action.
2. **"You never need to read."** Every word is spoken; every button has an icon; ages 5–7 never see text that matters.
3. **"I'll ask you, not just tell you."** The guide asks a question every 30–60 seconds.
4. **"If you don't get it, I'll explain it a different way."** No explanation is repeated word for word more than once.
5. **"You can't break anything or get stuck."** Mistakes are safe, progress always saves, and there is always a way forward.

---

## 11.2 First launch with no adult present

The first 2 minutes, step by step. **No account, no typing, no reading.**

| Step | What the child sees and hears | What the child does |
|---|---|---|
| 0 | The app picks its language from the device settings. A row of flag-and-face buttons is shown; each speaks a greeting in its language when touched: *"Tap the friend who talks like you!"* | Taps a language (the device language is preselected, so a single tap continues) |
| 1 | The app opens on the sleeping chessboard. A bell rings. Pip: *"Did you hear the bell? Tap the thumbs-up!"* 👍 / 👎 | 👍 continues. 👎, or no tap within 10 s, turns on subtitles and picture cues and shows an animated "turn up the sound 🔊" hint. (A web page can't detect a muted device, so we ask; the native apps also read the system volume.) |
| 2 | Pip: *"Hi! I'm Pip! How big are you?"* Three pictures: a small child, a middle child, a tall child, plus a small "I'm a grown-up" button. Then the chosen group shows only its 3–5 birthday cakes (5–7, 8–10, 11–15), each saying its number aloud | Two taps set the age band and the track (Pip for 5–10, Coach Nova for 11–15). "I'm a grown-up" opens parent setup. The age can be changed later behind the parent gate |
| 3 | Pip: *"Pick your face!"* Eight cartoon avatars (no photos, no names typed) | Taps an avatar → creates a local profile. Several kids on one device = several avatar faces on the start screen |
| 4 | Any age: Pip or Nova: *"Do you already know how chess pieces move?"* 👍 Yes · 🤔 A little · 👎 Not yet (voice-only for 5–7) | "Yes" or "a little" → 3-minute placement quest. "Not yet" → Level 0 (ages 5–6) or Level 1 |
| 5 | The first activity starts immediately. The child touches a piece within **30 seconds** of first launch | Plays |

**What a parent does (optional, any time):** a small "Grown-ups" corner icon opens the **parent gate** (a check that a young child can't pass). There are two strengths:
- **Simple gate** (a written instruction such as "Press and hold the 3 and the 7 together") for opening links and help pages only.
- **Parent PIN** (set by the parent at setup, or linked to the parent account) for time limits, purchases, AI features and account settings, because readers aged 8–15 could pass a simple gate.

Behind the gate: settings, time limits, cloud sync and account, reports, purchases. **Learning never requires it.**

**Privacy:** without an account, everything stays on the device: an avatar, a birth-year band, and progress. No
personal data, no network calls carrying identity. This keeps "play first" compatible with children's privacy laws.

---

## 11.3 Simple by design: the UI rules

| Rule | Detail |
|---|---|
| **One big next step** | The home screen shows Pip and one huge **▶ Continue** button that always launches the right next activity (lesson, review or game). Kids can ignore everything else |
| **Four doors, no menus** | Small doors under the Continue button: **📖 Learn · 🧩 Practise · ♟ Play · 🏆 My Trophies**. No menus deeper than 2 taps. Locked doors show a padlock, and Pip explains when they will open |
| **Max 3 choices on a screen** | For ages 5–7, never more than 3 answer options. For 8+, never more than 4 |
| **Icons + voice for every button** | Long-press any button to hear what it does |
| **Always-present helpers** | Bottom corner on every screen: **❓ Help** (Pip explains a different way), **🔁 Show me again** (replays the demo), **🏠 Home** (progress is saved first) |
| **Big targets, forgiving touch** | 48 dp minimum for buttons. **In lessons only**, a piece dropped very close to its target snaps onto it. **In games**, an illegal drop springs back, and older players can switch on move confirmation. A mis-tap on an empty square does nothing (no penalty) |
| **Tap-tap or drag** | Both work everywhere. Young children are shown tap-tap first (it's easier for small hands) |
| **No text-dependency for 5–7** | Subtitles are off by default; numbers are spoken; coordinates use picture letters |
| **Plain words** | ≤ 12 words per sentence for ages 5–10. Technical words come after the idea: *"…grown-ups call this castling."* |
| **No timers for young kids** | Nothing is timed below age 8, unless the child chooses a speed game |
| **Consistent colours** | Green = good or safe, red = danger, gold = reward, blue = hint. Always paired with shapes for colour-blind children |
| **No dead ends** | Every screen has a forward action. A failed Boss leads to Practice Camp, never a "Game Over" |
| **Auto-save always** | Progress is saved after every step. Closing the app mid-lesson resumes at the same step |

---

## 11.4 The guide that asks questions

Without an adult, the guide must constantly check understanding. Every lesson follows a **question rhythm**:

```
 Explain (≤ 20 s) → ASK → child answers → feedback (with WHY) → explain next bit → ASK …
```

### Rules for the guide's questions
- **A question at least every 30–60 seconds.** Never more than 20 seconds of talking without an interaction.
- **Predict before showing:** *"Where do you think the rook can go? Tap a square!"* Then the demonstration. Predicting first makes kids think instead of just watching.
- **Always explain why**, even when the answer is right: *"Yes! The bishop can reach it, because it's on a light square, just like him."*
- **Celebrate thinking, not luck:** *"You checked if the king was safe first. That's what champions do!"*
- **Wait time:** after asking, the guide waits silently (5 s for 5–7, 8 s for 8+) before offering any hint.
- **Teach-back at the end:** *"Now YOU be the teacher! Show Sparky how a knight moves."* The child demonstrates unaided. This is the lesson's real mastery check.
- **Spot Pip's mistake** (the "protégé effect"): Pip makes a deliberate error (*"I'll move my bishop to this dark square!"*) and the child corrects him. Children love catching the teacher's mistake, and it shows true understanding.

### The guide inside real games (coached games)
Practice games against bots are coached. Coaching fades as the child improves:

| Child level | Coaching in games |
|---|---|
| Levels 1–3 | Guide comments on most moves; **warns before blunders** ("Wait! Is your queen safe there? Look at that bishop"); in check, the king shakes and the guide says *"Check! Run, Capture or Block?"*; special moves are pointed out ("Psst, your king can castle now!") |
| Levels 4–6 | Warnings only for big blunders; the child may turn on the "Safety Check" shield before each move; take-backs allowed with an explanation |
| Levels 7–10 | No live help unless asked (❓ button); full post-game review |
| All levels | After the game: **3 key moments** at most, each as a question: *"Here you moved the knight. Can you find a better move?"* |

---

## 11.5 Question types

Twelve interaction types make up every lesson, practice set and boss. All work without reading.

| # | Type | Example | Ages |
|---|---|---|---|
| 1 | **Tap it** | "Tap the rook!" / "Tap the square e4!" | 5+ |
| 2 | **Move it** | "Move the knight to the carrot!" | 5+ |
| 3 | **Tap all** | "Tap EVERY square the bishop can reach" | 5+ |
| 4 | **Thumbs up / down** | "Is this king in check? 👍 / 👎" | 5+ |
| 5 | **Pick one** (2–3 picture options) | "Which piece can capture the pawn?" | 5+ |
| 6 | **Predict** | "What happens if the pawn moves two squares? Tap where it lands" → animation | 5+ |
| 7 | **Spot Pip's mistake** | Pip moves a rook diagonally: "Did I do it right?" 👍 / 👎 → "Show me the right way!" | 5+ |
| 8 | **Why?** (pick the reason) | "Why can't the king castle?" 🔴 in check · 🚶 already moved · 🧱 blocked | 7+ |
| 9 | **Sort it** | Swipe cards: Checkmate ⬅ / ➡ Stalemate | 6+ |
| 10 | **Count it** | "How many jumps for the knight to reach the star?" | 6+ |
| 11 | **Teach-back** | "Show Sparky all the ways to escape check" | 5+ |
| 12 | **Find it in a game** | During a coached game: "There's a fork here! Can you find it?" | 7+ |
| A1 | **Name it** (Academy) | Type or tap the notation: "Write the move: knight to f3" → Nf3 | 9+ |
| A2 | **Calculate** (Academy) | Play out a 2–4 move sequence; the bot responds | 10+ |
| A3 | **Speed round** (Academy, optional) | Timed puzzle streaks | 10+ |

---

## 11.6 When the child doesn't understand: teach it another way

Every concept is authored with **at least three explanation styles**. Hints rotate through them instead of repeating.

| Concept | 1 · Story | 2 · Visual / demonstration | 3 · Rule-of-thumb / physical |
|---|---|---|---|
| **Rook** | Captain Rook's tower is on wheels; wheels only roll straight | Glowing rails in four directions | "Like a ➕ sign!" Trace the plus with your finger |
| **Bishop** | Bishop Bo loves his colour and never leaves it | Diagonal light-beams; the opposite colour fades out | "Like an ✖!" |
| **Knight** | Sparky the horse can't walk straight; he jumps | Footprints making an L; a flower of 8 landing squares | "Two steps, then one to the side" / "Always jumps to the other colour" |
| **Pawn moves vs captures** | Pip marches forward bravely but fights sideways with his little sword | Forward arrow (move) vs diagonal swords (capture) | "Walk straight, fight diagonal" |
| **Check** | The king hears an alarm: danger! | A red laser from the attacker to the king | "Run, Capture, Block!" with 3 icons |
| **Checkmate** | The king is trapped in a room with no doors | Every escape square turns red, one by one | "Check + no escape = checkmate" |
| **Stalemate** | It's their turn, the king is safe, but they have no legal move at all, so it's a tie | Same picture as mate but without the laser | "No check + no moves = tie" |
| **Castling** | The king's secret door into his castle | Animated door; checklist lights | "King two steps, rook jumps over" |
| **En passant** | The ghost pawn left behind when a pawn runs past | A translucent ghost on the skipped square that fades after one turn | "Now or never!" |
| **Promotion** | Pip's dream of becoming a queen | Column of light, transformation | "Reach the end, pick a new piece" |

**The escalation path when a child gets an answer wrong:**

```
Wrong #1 → specific feedback ("That's a diagonal. Rooks only go straight!") + retry
Wrong #2 → switch to explanation style 2 + show the hint (highlight)
Wrong #3 → switch to style 3 + ghost-hand shows the move → child copies it
Still stuck → an easier version of the same task (fewer pieces / smaller board) → success
           → concept marked "needs review"; it returns tomorrow in a warm-up
```
The child **always ends on a success**, and the next question is an easy win.

---

## 11.7 Scenario playbook: what the app does when…

### A. Starting and sessions
| Scenario | App response |
|---|---|
| First launch, nobody helping | See 11.2. Voice-first, no account, in a lesson within 30 s |
| Sound is off or muted | Found by asking "Did you hear the bell?" (and, in the native apps, by reading the system volume): an animated 🔊 hint, subtitles and picture cues turn on, icons pulse |
| Child can't read | Default for ages 5–7. Every instruction is voiced, and long-press on anything repeats it |
| Child returns the next day | Pip greets them by avatar, does a 1-minute "Remember?" warm-up (spaced review), then ▶ Continue |
| Child returns after 2+ weeks | A longer friendly warm-up (5 questions) across recent concepts. Weak concepts are revisited before new content |
| Several children share one device | The start screen shows avatar faces; tapping one opens that child's progress. No names or passwords |
| A younger sibling picks up the device | Behaviour signals (much slower, random taps, failing mastered skills) → Pip: *"Is this a new friend? Tap your face!"* and an option to add a new avatar |
| Session time limit reached (set by parent) | Pip waits for a natural stopping point (end of a task), then: *"Great work today! Pip needs a nap. See you tomorrow!"* Saves and locks gently |
| Very long session, no limit set | Break suggestion at 15 / 25 / 45 minutes by age, with a stretching mini-animation. Never forced unless a parent set a limit |
| App closed mid-lesson | Resumes at the same step, with a 1-sentence recap |
| No internet | Everything in downloaded kingdoms works offline; progress syncs later (only if a parent enabled sync) |

### B. During a lesson
| Scenario | App response |
|---|---|
| Correct on the first try | Short praise + why it's right; slightly harder next item; quick pace |
| Correct after a hint | Praise for persistence; the same difficulty next time |
| Wrong answer | Escalation path (11.6). Feedback always names the *specific* rule ("Kings can't step next to the other king") |
| Tries an illegal move | The piece springs back; the guide explains *which* rule stops it (pinned, blocked, wrong shape, would be in check) and shows the legal squares |
| Idle 15–20 s | Gentle re-prompt; the target glows |
| Idle 45–60 s | Re-explain using a different style; *"Need help? Tap me!"* |
| Idle 3+ minutes | Auto-pause and save; Pip falls asleep (snoring); a tap wakes him with a recap |
| Random rapid tapping (frustration or play) | Pip: *"Whoa! Let's slow down. Take a big breath with me…"* (5-second breathing animation), then an easier item |
| Fast guessing (quick wrong answers) | *"Take your time. Champions look before they move!"*, with a 2-second "think" pause before answers are accepted |
| Taps ❓ Help | The guide explains in the *next* explanation style, not the same words |
| Taps 🔁 Show me again | Replays the demonstration, slower, with highlights |
| Wants to skip the story | The story can be skipped after the first viewing; the questions remain |
| Clearly bored (fast, perfect answers) | *"Too easy? Let's make it harder!"* → challenge items, or offer a skip-ahead test |
| Leaves in the middle repeatedly at the same lesson | Lesson flagged; next time it starts with a shorter, easier version and a fun mini-game first |

### C. Playing games
| Scenario | App response |
|---|---|
| About to blunder a piece (beginner levels) | Pre-move warning: the piece shakes, *"Is it safe there? Look at the knight!"* Child may still play it (learning by consequence) |
| In check and doesn't notice | The king shakes, red laser, *"Check! Run, Capture or Block?"* Only legal escapes are possible |
| Can castle for the first time | *"Psst! Your king can use the secret door now!"* (Levels 3–4 only) |
| En passant becomes possible | The ghost pawn appears; *"Remember the ghost pawn?"* (first few times only) |
| Pawn reaches the last rank | Promotion picker with 4 big icons; Queen recommended for young kids; underpromotion puzzles later |
| Gives stalemate when winning | The game ends as a draw, then: *"Oh no, a sneaky tie! Let's see how to make it checkmate instead"* → 30-second replay lesson |
| Wins | Big celebration; the next bot is offered; the difficulty of the current bot rises |
| Loses | Encouragement (*"Every champion loses. Let's see one thing to learn!"*), a review of 1 key moment, a rematch or easier bot offered |
| Loses 3 in a row | Automatic easier bot + suggestion of a short related lesson. No "you lost" counters |
| Wins 3 in a row easily | Suggest the next bot; for older kids, introduce a rating |
| Repetition or 50-move situation | The guide says *"You can claim a draw! Tap here if you want a tie,"* with a short explanation, as in real chess for every age. Fivefold repetition and the 75-move rule end the game automatically |
| Insufficient material (for example, K vs K) | Automatic draw: *"Nobody can checkmate any more, so it's a tie!"* |
| Wants to stop mid-game | **Save for later** or **Resign** (explained: *"Resigning means you give up this game. That's OK!"*) |
| Wants to play a parent or friend | Pass-and-play on one device; the board turns around; the coach explains to both players |

### D. Emotions and motivation
| Scenario | App response |
|---|---|
| Signs of frustration (many errors, rapid taps, quitting) | Easier tasks, a fun mini-game break, warm encouragement; the hardest content is postponed |
| Left the app angry (quit after failures) | Next launch begins with a guaranteed easy win and *"Welcome back, champion!"* |
| "I just want to play!" | The ♟ Play door is always open for coached games (from Level 2); learning content is suggested, never forced |
| Missed several days | No guilt messages. *"I missed you! Ready for an adventure?"* Streaks count "days this week", not consecutive days |
| Finishes a level | Celebration, certificate on screen, *"Show a grown-up!"* button (opens the trophy view; optional) |
| Fails a Boss | Practice Camp: 2 short targeted activities, then retry. The boss "remembers" and cheers: *"You came back stronger!"* |
| Fails the same Boss 3 or more times | An alternative route: a different, easier set of practice activities, a "helper" bonus heart, and a gentle note in the parent report suggesting they play a game together |
| Stuck on the same level for weeks (Levels 7–10) | Training Plan suggests a different kind of practice (endgames instead of openings, model games instead of puzzles) and celebrates small gains |
| Upset by a bot's reaction | Bots never taunt. Cheeky characters only joke about themselves ("Oops, I left my knight!"). Any line can be reported by a parent and removed |
| Always wants to play White | The guide encourages alternating ("Champions can play both colours!"); bots alternate colours by default |
| Believes a wrong "house rule" | The guide explains the real rule kindly and points to "Chess Myths Busted!" (Lesson 3.15) |

### E. Technical
| Scenario | App response |
|---|---|
| Slow or old device | Automatic 2D mode or low-quality 3D; the child is never asked about graphics settings |
| Screen rotated | The board re-centres; portrait and landscape are both supported |
| Audio fails to load | Subtitles + icon animations + vibration feedback |
| App updated mid-progress | Progress migrates automatically; a "What's new" visit from Pip, only if it's relevant to the child |
| App sent to the background during a Boss | The Boss pauses and resumes exactly where it was; no hearts are lost |
| Device reinstalled or replaced | If the profile was linked to a parent account, it restores in one tap. If not, the parent-gated "Save my progress" prompt after Level 1 is the protection (see document 7) |
| Device clock changed to dodge a time limit | Limits use the parent account's server time when online, and the app's own play-time counter when offline |
| A sibling plays on the wrong avatar | The behaviour signals from scenario A suggest "Is this you?"; a parent can move recent progress between profiles in the parent hub |

### F. Safety
| Scenario | App response |
|---|---|
| Child taps something that would cost money, open a link, or change settings | Parent gate. The child sees a friendly *"Ask a grown-up for this one!"* |
| Child wants to play online with strangers | Not possible. Friend games need invite codes and parent approval |
| Child wants to type their name | Never asked. Avatars only |
| Taps Resign or Home by accident | Resign always needs a second, clearly different confirmation ("Are you sure? 🏳️ / Keep playing ♟"). Home saves the game first |

### G. Accessibility
| Scenario | App response |
|---|---|
| Deaf or hard-of-hearing child | Visual-only demonstration mode: every spoken line has a picture-and-animation version, captions with icons, and vibration feedback. Sign-language videos for key concepts in supported languages (later phase) |
| Blind or low-vision child | Audio chess mode: squares and moves are announced, moves are entered by voice (on-device) or keyboard, and a tactile-board companion guide is offered |
| Motor difficulties | Tap-tap only (no dragging needed), larger squares in 2D mode, adjustable touch hold time, switch-access support |

### H. Memory and mastery
| Scenario | App response |
|---|---|
| Forgets an old rule | Spaced repetition notices the weak concept → it appears in "Remember?" warm-ups and in Boss rounds |
| Revisits an old level by choice | Allowed any time; stars can be improved |
| Already knows the rules | Placement quest; Levels 1–3 can be passed in about 10 minutes through "Prove it!" challenges |
| Wants the app to referee a real-board game | **Referee mode:** the child taps (or, with an electronic board, plays) the moves of a real game; the guide answers "Can I castle here?", spots illegal moves, and runs a chess clock |

---

## 11.8 Adapting both ways: too easy and too hard

| Signal | Interpretation | Adaptation |
|---|---|---|
| ≥ 90% correct, fast, no hints over 10 items | Too easy | "Prove it!" challenge → skip ahead; harder practice variants; stronger bot |
| 70–85% correct | Just right | Keep going |
| < 60% correct or 3 wrong in a row | Too hard | Switch explanation style, easier variant, smaller board, more guided steps |
| Rapid taps, long idle, early exits | Frustration or disengagement | Mini-game break, easier win, shorter session suggestion |

- Every lesson has a **"Too easy? Prove it!" ⚡ button** (any age; voice-led for 5–7) that runs the lesson's check questions immediately. Passing it completes the lesson.
- The **placement quest** (3 minutes, 12 adaptive questions on a 3D board) can place an experienced child directly at Levels 2–5.

---

## 11.9 Rules coverage matrix: every scenario taught and tested

Every rule and edge case from [document 2](02-chess-rules-reference.md) must have: a lesson that teaches it, a practice task,
a check question, and coverage in a Boss or coached game. Missing coverage fails the content build in CI.

| Rule / scenario | Taught in | Practice | Question type(s) | Boss / game check |
|---|---|---|---|---|
| Using the app's board: select, dots and rings, move, cancel, switch, drag, rotate, zoom, reset, 2D/3D, help buttons | 1.2 | Wake the Pieces | Move it, Tap it | L1 Boss |
| Piece names, shapes, how many (16 per side, 32 in total) | 1.3 | Who's Who? | Tap it, Pick one, Spot Pip's mistake | L1 Boss |
| 64 squares, light and dark, 8 × 8 | 1.4 | File & Rank Catch | Count it, Thumbs up / down | L1 Boss |
| Board orientation (light on the right) | 1.4, 1.12 | Build the Army | Spot Pip's mistake (board rotated) | L1 Boss |
| Types of chessboards and sets; real chess is always 8 × 8 | 1.5 | — | Sort it, Thumbs up / down | L1 Boss |
| Files | 1.6 | File & Rank Catch | Tap all | L1 Boss |
| Ranks | 1.7 | File & Rank Catch | Tap all | L1 Boss |
| Diagonals; long diagonals | 1.8 | File & Rank Catch | Tap all | L1 Boss |
| Coordinates (square names) | 1.9 | Coordinate Rush | Tap it, Pick one | L1 Boss |
| Board map: centre, kingside, queenside, halves, back ranks, edges, corners | 1.10 | Board Map Quiz | Tap it, Pick one | L1 Boss |
| 2D diagrams and symbols; the board from Black's side | 1.11 | Who's Who? (2D round) | Pick one, Tap it | L1 Boss |
| Initial setup, queen on her colour | 1.12 | Build the Army: Speed Run | Spot Pip's mistake (queen and king swapped) | L1 Boss |
| White moves first; moves, turns and captures | 1.13 | Taking-turns practice board (two pieces only) | Thumbs up / down | L1 Boss, L3 game |
| Rook movement and blocking | 2.1, 2.3 | Star Collector | Tap all, Count it | L2 Boss |
| Bishop movement; colour-bound | 2.4 | Star Collector (impossible stars) | Why?, Thumbs up / down | L2 Boss |
| Queen movement | 2.6 | Hungry Pieces | Tap all | L2 Boss |
| King movement; never into danger; kings never adjacent | 2.7 | King's Walk | Tap all (safe squares), Spot Pip's mistake | L2 Boss, coached games |
| Knight movement; jumping; colour change | 2.9 | Knight's Quest | Tap all, Count it | L2 Boss |
| Pawn move; first-move double step; blocked pawns | 2.11 | Pawn Wars | Predict, Thumbs up / down | L2 Boss |
| Pawn diagonal capture; no straight capture | 2.12 | Pawn Wars | Spot Pip's mistake | L2 Boss |
| Can't capture own pieces; can't jump (except the knight) | 2.3 | Star Collector | Thumbs up / down | L2 Boss |
| Piece values (points) | 2.14, 4.1 | Hungry Pieces | Pick one (best capture), Count it | L2 Boss, L4 Boss |
| Game points: win 1, draw ½, loss 0; how results are written | 3.14 | Tournament table game | Count it, Pick one | L3 Boss |
| Check: recognising it | 3.1 | Is It Check? | Thumbs up / down | L3 Boss, coached games |
| Escaping check: run, capture, block | 3.2 | Escape drills | Why?, Move it | L3 Boss |
| Knight / pawn checks can't be blocked | 3.2 | Escape drills | Why? | L3 Boss |
| Double check: only the king can move | 3.2 (8+) | Escape drills | Move it | L3 Boss |
| Can't move into check; pinned pieces can't move off the line | 3.3 | Safe moves | Spot Pip's mistake | L3 Boss |
| A pinned piece can still give check | 5.4 | Pin puzzles | Thumbs up / down | L5 Boss |
| Checkmate | 3.4, 3.5 | Mate-in-1 Ladder | Sort it, Move it | L3 Boss |
| Stalemate = draw | 3.6, 3.7 | Mate or Stalemate? | Sort it, Why? | L3 Boss, L6 endgames |
| Castling: how (both sides) | 3.8 | Castle drills | Move it | L3 Boss |
| Castling: each of the 6 conditions | 3.8 | "Can White castle?" set | Why? (one item per condition) | L3 Boss |
| Castling: rook may pass an attacked b1/b8 | 3.8 (8+) | Castle drills | Thumbs up / down | L3 Boss (Explorers and Academy) |
| Castling rights lost after a king or rook move | 3.8 | Castle drills | Why? | L3 Boss |
| Promotion: must promote; Q/R/B/N; several queens possible | 3.9 | Pawn Wars | Pick one, Predict | L3 Boss |
| Underpromotion (knight check; avoiding stalemate) | 6.12 | Promotion puzzles | Move it | L6 Boss |
| En passant: how; only the very next move | 3.10 | Ghost-pawn set | Thumbs up / down (with trick items) | L3 Boss |
| En passant illegal if it exposes the king | 3.10 (advanced step, unlocked by skill) | Ghost-pawn set | Why? | L5 Boss |
| Draw: dead position / insufficient material (and blocked pawns, 8+) | 3.13 | Draw sorting | Sort it | L3 Boss |
| Draw: threefold (claim) / fivefold (automatic) repetition | 3.13, 10.5 | Repetition demo | Predict | L10 Arbiter Academy |
| Draw: 50-move (claim) / 75-move (automatic) rule | 3.13, 10.5 | Counter demo | Thumbs up / down | L10 Arbiter Academy |
| Draw by agreement; offering a draw correctly | 3.12, 10.5 | Coached games | Pick one | L3 Boss, L10 |
| Timeout: loss if the opponent could still mate by any legal moves; draw if not | 3.12, 10.2 | Clock games | Why? | L10 tournament |
| Win by resignation or timeout | 3.12, 10.2 | Coached games | Pick one | L3 Boss, L10 tournament |
| Touch-move, "I adjust", completing a move | 3.16 (basics), 10.4 | Arbiter role-play | Spot Pip's mistake | L10 Boss |
| Illegal-move penalties (including pressing the clock without moving, promotion-piece rules) | 10.4 | Arbiter role-play | Pick one | L10 Boss |
| Notation (all symbols) | 4.19 (Explorers and Academy; voice-only for Little Knights), 10.1 scoresheets | Scoresheet Scribe | Name it | L4 Boss, L10 Boss |
| Clocks and time controls (increment, simple and Bronstein delay) | 4.20 (basics), 10.2 | Clock Challenge | Pick one | L10 tournament |
| Etiquette and sportsmanship | 0.7, 3.16, 10.7 | Role-play | Pick one | L3 Boss, L10 |
| Discovered check, check by promotion, check by castling | 3.11 | Sneaky Check Spotter | Tap it | L3 Boss |
| Common rule myths | 3.15 | Myth Buster | Thumbs up / down | L3 Boss |
| Playing on a real board (touch-move, one hand, handshake) | 3.16 | Real Board Challenge | Teach-back on a real board | L3 Boss |
| Scoresheet rules (never write a move in advance; under-5-minute exception) | 10.1 | Scoresheet Scribe | Spot Pip's mistake | L10 Boss |
| Draw offers and claims: correct procedure | 10.5 | Arbiter Says | Pick one | L10 Boss |
| Rapid and blitz rule differences | 10.6 | Arbiter Says | Pick one | L10 Boss |
| Chess960 setup and castling | 10.18 (optional) | Chess960 games | Move it | — |

---

## 11.10 Daily self-guided loop (about 10 minutes)

```
▶ Continue
  1. Remember? warm-up      — 3 quick review questions (spaced repetition)     ~1 min
  2. Today's lesson          — one concept, question every 30–60 s               ~4 min
  3. Practise                — mini-game or puzzles at the right difficulty      ~3 min
  4. Coached game / challenge — apply it with the guide watching                 ~3 min
  5. Celebrate               — stars, map step forward, "See you tomorrow!"
```

A child who only ever taps **▶ Continue** will complete the entire curriculum in the right order, with review built in.
That is the core test of a self-guided design.

---

## 11.11 Moving from Pip to Nova

The guide is chosen by age band, but children change. The rules:
- A birthday never switches the guide in the middle of a level. At the next level boundary, the child (and, if linked, the parent) is asked: *"Do you want to keep learning with Pip, or meet Coach Nova?"*
- Choosing Nova plays a short hand-over scene: Pip introduces Nova and says goodbye. Pip stays available as an optional "buddy" in the corner.
- A parent can choose either guide at any age in the parent hub (for example Nova for a mature 9-year-old, or Pip for a 12-year-old beginner).

## 11.12 Strong young children

A 6-year-old can be a strong player. Skill unlocks content at any age, and Little Knights get adapted versions of advanced material:
- Notation is spoken ("Knight to f3"), and picture scoresheets show piece icons instead of letters.
- Opening lessons use arrows and animations instead of move lists.
- A parent can switch on Nova's voice and full text at any age.

## 11.13 Asking "why?" after teach-back

For ages 7 and up, every teach-back ends with one "Why?" question (pick the reason from 2–3 pictures). Getting the move right is not enough to master a concept; the child must also pick the right reason.
