# 4. Lesson Scripts

Screenplay-style scripts for the content, voice-over, animation and development teams. Each script is
the blueprint for a lesson file in the lesson scripting format (see [Technical Architecture](07-technical-architecture.md#74-lesson-scripting-format)).

## 4.1 Script conventions

```
SCENE      – what the 3D world shows (camera, lighting, board state)
PIP / NOVA – spoken line (voice-over) — also shown as subtitle in Explorers/Academy tracks
ACTION     – animation or effect
INTERACT   – what the child must do (tap, drag, choose)
  ✔ SUCCESS – feedback when correct
  ✘ RETRY   – feedback when wrong (never shaming; always a hint)
REWARD     – stars, sticker, XP, unlock
[LK] [EX] [AC] – line variants for Little Knights / Explorers / Academy
```

> **Voice policy (after critique rounds 1 and 2):** there are two *guide* voice sets: **Pip** (LK and EX) and **Nova** (AC).
> Explorers reuse the LK guide lines with subtitles; [EX] variants change practice difficulty, rewards and
> on-screen text, not the recording. The **supporting cast** (King Bram, Queen Stella, Captain Rook, Sparky,
> Bishop Bo, bosses and bots) is recorded once per language and shared by every track. Every lesson must also follow the self-guided rules in
> [document 11](11-self-guided-learning.md): a question every 30–60 seconds, three explanation styles per concept,
> a "Spot Pip's mistake" item, and a teach-back at the end.

**The lesson rhythm (every lesson):**
0. **Remember?** (≤ 30 s): one retrieval question from an earlier lesson.
1. **Hook** (≤ 20 s): a story moment or a question.
2. **Watch** (I do): the character demonstrates in 3D.
3. **Try** (we do): a guided move with highlighted hints.
4. **Practise** (you do): 3–6 tasks of increasing difficulty, with hints available.
5. **Check:** at least 5 quick items of at least 2 question types; 4 of 5 correct masters the lesson. This is the mastery data.
6. **Celebrate and connect:** reward, plus "next time…" teaser.

**Hint ladder** (used in all INTERACT steps):
1. Verbal nudge ("Remember, the rook goes in straight lines!").
2. Highlight the area or piece.
3. Show the legal-move dots.
4. Ghost-hand demonstrates, then the child repeats it.

---

## 4.2 Characters

| Character | Role | Voice direction |
|---|---|---|
| **Pip the Pawn** | Main guide (5–10). A small, brave pawn who dreams of reaching the last rank and becoming a Queen. His journey mirrors the child's | Warm, excited, curious; age about 8; never sarcastic |
| **Captain Rook** | Supporting character in every track, and co-guide for Explorers (8–10). A friendly tower-captain, strong and steady. Never an opponent | Hearty, a little pirate-ish |
| **Queen Stella** | Appears at milestones; the "goal" Pip dreams of | Kind, regal, encouraging |
| **King Bram** | Comic relief; a slightly nervous, very important king | Fussy and funny ("Careful! I'm VERY important!") |
| **Sparky the Knight** | A jumpy horse who never walks straight | Energetic, giggly |
| **Bishop Bo** | A gentle bishop who loves his colour and never leaves it | Calm, kind |
| **Bosses and bots** | Friendly rivals at each kingdom gate and in the Play Zone (never the guides) | Playful, never scary or mean; no taunting |
| **Coach Nova** | Academy guide (11–15). A young titled player and coach | Clear, respectful, a bit witty, treats teens as players |

---

## 4.3 Lesson 1.1 — "Welcome to Chess Land" (full script, Little Knights)

**Objective:** the child knows there are two armies, each with a king, and the goal is to trap the enemy king.
**Duration:** about 3 min.

```
SCENE   Sunrise over a toy-like 3D valley. Camera swoops down to a wooden chessboard
        sitting on a hill. Pieces are asleep (closed eyes, gentle snoring sound).
ACTION  A small pawn on e2 yawns, opens eyes, hops up and down.

PIP     "Oh! Hello! You woke me up! I'm Pip — Pip the Pawn!"
PIP     "Welcome to Chess Land! This is our magic board."

ACTION  All white pieces wake up and wave. Black pieces wake up on the other side and wave.
PIP     "We are the White team. Over there is the Black team. Say hi!"
INTERACT Tap the Black team to wave at them.
  ✔ SUCCESS  Black pieces wave back. Happy chime. PIP: "They like you!"
  ✘ RETRY    (any other tap) Black team glows softly. PIP: "They're on the far side — tap them!"

ACTION  Camera zooms to the white King (e1). He adjusts his crown, nervous.
KING    "Ahem! I am King Bram. I'm the MOST important piece. Please keep me safe!"
PIP     "Every team has one King. Our job is to protect OUR King…"
ACTION  Camera pans to the Black King, who smirks playfully.
PIP     "…and to trap THEIR King, so he can't run away. That's how you win!"

ACTION  Quick 5-second "dream" animation: Black king surrounded by white pieces,
        looks left/right, nowhere to go; golden "CHECKMATE!" banner, confetti.
PIP     "When the King is trapped, we call it… CHECKMATE!"
INTERACT Tap the King you must protect.
  ✔ SUCCESS  White King bows. PIP: "Yes! That's our King!"
  ✘ RETRY    (tapped Black King) PIP: "That's their King — we want to trap him. Which King is ours?" 
             (white King sparkles)
  ✘ RETRY    (tapped other piece) PIP: "Look for the crown with the little cross on top!"

PIP     "I have a secret dream… If I march all the way to the other side,
         I can become a QUEEN! Will you help me get there?"
INTERACT Big "YES!" button (Pip hugs camera).
REWARD  ⭐⭐⭐ + sticker "Chess Land Visitor". Map: path to "Your Magic Board" lights up.
PIP     "Next time, I'll show you how to wake us up and move us!"
```

**[EX] variant:** same scene; Pip's lines are shortened and shown as subtitles. Captain Rook adds:
"Every great general knows the goal first. Trap the enemy king!"
**[AC] variant:** Coach Nova, realistic board, 60-second cinematic: *"Chess is a battle between two armies.
You win by checkmate: attacking the enemy king so it can't escape. Everything we learn serves that goal."*

---

## 4.4 Lesson 1.2 — "Your Magic Board: Tap, Move and Look Around" (how to use the app's board)

**Objective:** the child can select a piece, understand the dots and rings, move by tapping or dragging, cancel a
selection, turn and zoom the board, and use the help buttons, all without an adult. **Duration:** about 4 min.
This lesson comes *before* any piece movement, so later lessons never fail because the child doesn't know how to use the app.

```
SCENE   Board with only three white pieces, all asleep: a rook on a1, a knight on g1, a pawn on e2.
PIP     "These pieces are sleepy! Tap one to wake it up!"
INTERACT Tap any piece.
  ✔ SUCCESS  The piece yawns, LIFTS up a little, and glows gold. Soft "tock" sound.
PIP     "You picked it up! See it glowing? That means it's chosen."
ACTION  Small green DOTS appear on the squares the piece can go to.
PIP     "The little dots show where it can go. Tap a dot!"
INTERACT Tap a dot.
  ✔ SUCCESS  The piece glides there and lands with a wooden "clack". A soft yellow
             glow stays on the start and end squares.
PIP     "It moved! The yellow glow shows the last move, so you never forget what happened."
  ✘ RETRY   (taps a square with no dot) Gentle "bonk", the dots pulse.
             PIP: "Not there. Tap a square with a dot!"

PIP     "Changed your mind? Tap the glowing piece again to put it back down."
INTERACT Select a piece, then tap it again. → It settles down; the dots disappear.
PIP     "Want a different piece? Just tap the other one."
INTERACT Select the rook, then tap the knight. → The selection jumps to the knight.

ACTION  A black pawn appears on a square the knight can reach. It shows a RING instead of a dot.
PIP     "A ring around an enemy piece means you can capture it!"
INTERACT Capture the pawn. → It bows and walks off to the side "bench" (captured-pieces tray).

PIP     "There's another way to move. Press on a piece, keep your finger down, slide it, and let go!"
ACTION  A ghost hand demonstrates a drag. The square under the finger lights up.
INTERACT Drag a piece to a dot.
  ✘ RETRY   (drops it on a wrong square) It springs back home.
             PIP: "Oops, it bounced back! Let go on a dot."

PIP     "You can look around too! Slide your finger on the table, not on a piece, to turn the board."
INTERACT Turn the board. (Turning is limited, so the board can't get lost.)
PIP     "Pinch with two fingers to zoom in and out."
INTERACT Zoom.
PIP     "Lost? Tap the target button 🎯 to see the board the normal way again."
INTERACT Tap Reset view.
PIP     "And this button makes the board flat, like a picture in a book. Tap it again for 3D!"
INTERACT Toggle 2D / 3D twice.

ACTION  The ❓ 🔁 🏠 buttons glow one at a time.
PIP     "If you ever need me, tap the question mark. To see something again, tap the circle arrow.
         The little house takes you home, and I always save your game first!"
INTERACT Tap ❓ → Pip waves: "I'm always here!"

INTERACT (Check) "Wake the Pieces": 5 tasks: select and move by tapping, change your mind, capture with a
         ring, move by dragging, flip to 2D and back.
REWARD  ⭐⭐⭐ + sticker "Board Boss". Unlocks the mini-game "Wake the Pieces".
```

**Interaction rules this lesson teaches (they hold everywhere in the app):**

| Action | Result |
|---|---|
| Tap your own piece | Selects it: it lifts, glows gold, and shows the legal squares |
| Dot on a square | The selected piece can move there |
| Ring around an enemy piece | The selected piece can capture it |
| Tap a dot or ring | Moves there |
| Tap the selected piece again | Cancels the selection |
| Tap a different piece of yours | Switches the selection |
| Tap an empty square with no dot | Nothing happens (a soft hint, no penalty) |
| Press, slide and release | Drag move; it springs back if the square isn't legal, and the guide explains why |
| Yellow glow on two squares | The last move played |
| Red glow under a king | That king is in check |
| Slide on the table / pinch | Turn / zoom the board (limited) |
| 🎯 Reset view · 2D/3D · 🔄 Flip | Standard view · flat or 3D · see from the other side |

**[AC] variant:** Coach Nova covers the same in 40 seconds, plus Academy extras: turning legal-move dots off (as in real tournaments),
drawing arrows and circles on the analysis board, keyboard control (arrow keys + Enter), and move confirmation.

---

## 4.5 Lesson 1.3 — "Meet the Pieces"

```
SCENE   A parade ground. The white army marches in, one piece type at a time; each stops on a pedestal.
PIP     "Let's meet the team! Everyone has a special hat, so you can tell them apart."
ACTION  King steps forward; his cross sparkles.
KING    "I'm the King: the tallest, with a cross on top. There's only one of me!"
ACTION  Queen steps forward; her crown sparkles.
QUEEN   "I'm the Queen, with a crown. Only one of me too!"
ACTION  Two Rooks roll in.  ROOK: "We're the Rooks, castle towers! There are two of us."
ACTION  Two Bishops.        BISHOP: "Bishops have a pointy hat with a little cut in it. Two of us!"
ACTION  Two Knights neigh.  SPARKY: "Knights look like horses! Two of us!"
ACTION  Eight Pawns march.  PIP: "And us, the Pawns! Small, with round heads. There are EIGHT of us!"
PIP     "Let's count: 1 King, 1 Queen, 2 Rooks, 2 Bishops, 2 Knights, 8 Pawns. That's 16!"
ACTION  The black army marches in on the other side. "The Black army has 16 too. 32 pieces in all!"

INTERACT (Who's Who?) "Tap the Queen!" / "Tap ALL the Knights!" / "Which one is the Bishop?" (3 choices)
INTERACT (Spot Pip's mistake) Pip points at a Bishop: "This is the Queen, right?" 👍 / 👎
         → "Show me the real Queen!"
INTERACT [EX/AC] Match each 3D piece to its 2D symbol ♔ ♕ ♖ ♗ ♘ ♙, then [AC] to its letter K Q R B N
         (pawns have no letter).
REWARD  ⭐⭐⭐ + sticker "Team Captain". Unlocks the mini-game "Who's Who?".
```

---

## 4.6 Lesson 1.5 — "Chessboards Around the World"

```
SCENE   Pip opens a magic picture book. Each page "zooms" the camera into a new place with a different board.
PIP     "Chess is played everywhere! Let's go on a trip to see different chessboards."
ACTION  Page 1, a living room: a wooden board with wooden pieces.  PIP: "A wooden board at home!"
ACTION  Page 2, a school hall: rows of green-and-white roll-up boards with letters and numbers on the edges.
PIP     "In a chess club or tournament, boards often roll up like a mat. See the letters and numbers on the side?"
ACTION  Page 3, a car: a tiny magnetic travel set.  PIP: "Magnets keep the pieces on during a bumpy ride!"
ACTION  Page 4, a park: giant pieces as tall as children.  PIP: "Giant chess! You carry the pieces in your arms!"
ACTION  Page 5, a classroom: a teacher's board hanging on the wall.  PIP: "Teachers use a big board on the wall."
ACTION  Page 6, a big tournament: a board with lights that sends the moves to a screen.
PIP     "Some special boards tell a computer every move, so people all over the world can watch!"
ACTION  Page 7, a book: a flat 2D diagram.  PIP: "In books, the board is a flat picture."
ACTION  Page 8, back to our 3D board.  PIP: "And here's ours: the magic 3D board!"

PIP     "Here's a secret. Every real chessboard has… 8 squares this way and 8 that way! Always the same."
ACTION  A small 4×4 practice board appears with a "Practice!" sign.
PIP     "Sometimes we practise on little boards, but REAL chess is always 8 by 8."
PIP     "And even if the squares are green or brown, we still call them the light squares and the dark squares!"

INTERACT (Sort it) Swipe cards: "Real chess board ✅" vs "Practice board 🧩" (an 8×8 green board, a 6×6 board,
         a giant 8×8 park board, a 5×5 board, a 2D diagram…).
INTERACT (Thumbs up/down) A green-and-white board: "Is this a real chessboard?" 👍
INTERACT [AC] Coach Nova adds: the Staunton piece design, FIDE tournament equipment sizes,
         and electronic boards used for live broadcasts.
REWARD  ⭐⭐⭐ + sticker "World Traveller".
```

---

## 4.7 Lesson 1.9 — "Every Square Has an Address" (coordinates)

```
SCENE   Board viewed from directly above (top-down mode). Each file is a coloured lane.
PIP     "The board is a city! Every square is a little house with an address."
ACTION  Letters a–h pop up below the board; [LK] each with a picture:
        a=🍎 apple, b=⚽ ball, c=🐱 cat, d=🐶 dog, e=🥚 egg, f=🐟 fish, g=🍇 grapes, h=🏠 house.
PIP     "These streets go UP. Their names are a, b, c, d, e, f, g, h."
ACTION  Numbers 1–8 rise up the left side like floors of a building.
PIP     "And these are the floors: 1, 2, 3… all the way up to 8!"
ACTION  A glowing finger traces e-lane up to floor 4; square e4 lights up with a doorbell "ding-dong".
PIP     "Egg street, floor 4. That's e4! Letter first, then number."

INTERACT (Try) "Find d2 — dog street, floor 2." Lane d glows faintly.
  ✔ SUCCESS  Doorbell, a tiny house character opens the door and waves.
  ✘ RETRY    Hint ladder: lane glows → floor glows → square pulses.

INTERACT (Practise) 5 squares: a1, h8, e4, c6, g3 — Pip delivers a letter to each house.
INTERACT (Check)    Reverse: square glows → choose its name from 3 picture-cards.
REWARD  ⭐ per accuracy band; sticker "Postman Pip".
```
**[AC] variant:** Coach Nova adds "Diagonals have names too: the long diagonal a1–h8" and launches *Coordinate Rush* (30 s timer, personal best tracked, white and black perspectives).

---

## 4.8 Lesson 1.10 — "The Board Map"

```
SCENE   Top-down view. The board becomes a little island map with areas that light up.
PIP     "Let's learn the board's map, so you always know where things are!"
ACTION  d4, e4, d5, e5 glow gold and a little flag pops up.
PIP     "These four squares in the middle are the CENTRE. It's the best place to be!"
ACTION  Files e–h glow blue under the King.  PIP: "The King's side is called the KINGSIDE."
ACTION  Files a–d glow purple under the Queen.  PIP: "The Queen's side is called the QUEENSIDE."
ACTION  Ranks 1–4 tint white, 5–8 tint black.  PIP: "This half is White's land, that half is Black's land."
ACTION  Rank 1 and rank 8 glow.  PIP: "The very back rows are the BACK RANKS, where the big pieces live."
ACTION  Rank 8 sparkles with a rainbow.  PIP: "And if I reach Black's back rank… that's my dream row!"
ACTION  Corners and edges glow.  PIP: "These are the edges and corners."

INTERACT (Board Map Quiz) "Tap the centre!" / "Is this square on the kingside or the queenside?" /
         "Tap Black's back rank" / "Tap a corner".
INTERACT [EX/AC] Flip the board to Black's view: "Where is a1 now?" (it's top-right from Black's side).
REWARD  ⭐⭐⭐ + sticker "Map Reader". Unlocks "Board Map Quiz".
```

**Lesson 1.11 "Same Board, Two Views"** follows the same pattern. The 3D board slowly flattens into a 2D diagram
while each piece morphs into its symbol. The child matches pieces across the two views, then practises
reading a diagram from a book page and seeing the board from Black's side.

---

## 4.9 Lesson 1.12 — "Build the Army" (setup)

```
SCENE   Empty board; pieces wait in a toy chest beside it.
PIP     "Time to build our army! First — turn the board the right way.
         Light on the right!"
INTERACT Tap the turn-board button 🔄 (it turns the board a quarter at a time) until the bottom-right corner is light.
  ✔ SUCCESS  Corner square twinkles. "Light on the right!" chant with a little drum beat.
CAPTAIN ROOK "Towers go in the corners — that's us rooks!"
INTERACT Drag both Rooks to a1/h1.
SPARKY  "Then us horses — right next to the towers! Neigh!"
INTERACT Drag Knights to b1/g1.
PIP     "Then the bishops, next to the horses."
INTERACT Drag Bishops to c1/f1.
QUEEN STELLA "And I go on my own colour — my favourite dress matches the square!"
ACTION  Queen's dress shimmers light; d1 shimmers light.
INTERACT Drag Queen to d1.
  ✘ RETRY  (placed on e1) Queen: "Hmm, that square is dark — I like to match!"
KING    "And I get the last spot. Next to my Queen, of course!"
INTERACT Drag King to e1.
PIP     "And we pawns stand in front, like a wall!" (pawns march in automatically for LK; drag for EX/AC)
ACTION  Black army sets itself up as a mirror; the two Queens wave to each other across the d-file.
PIP     "See? Queen faces Queen, King faces King!"
REWARD  ⭐⭐⭐ + unlock mini-game "Build the Army: Speed Run".
```

---

## 4.10 Lesson 2.1 — "Captain Rook's Straight Roads"

```
SCENE   Tower Town. Board with ONLY a white Rook on d4. Camera at child's-eye 3/4 angle.
ROOK    "Ahoy! I'm Captain Rook. I roll in straight lines — like a plus sign!"
ACTION  Four glowing rails extend from d4: up, down, left, right, to the board edges.
ROOK    "Forward, back, left, right — as far as I like, until something's in the way!"
ACTION  Rook rolls d4→d8 (wheels squeak), then d8→a8, with a satisfying "thunk" on landing.

INTERACT (Try)   A star appears on d7. "Roll me to the star!" Legal-move dots shown.
  ✔ SUCCESS  Star bursts into sparkles. ROOK: "Straight as an arrow!"
INTERACT (Try)   Star on f6 (needs 2 moves). Dots hidden for EX/AC.
  ✘ RETRY   (attempt diagonal drag) Rook shakes head, rails flash. 
            ROOK: "No diagonals for me, matey! Straight lines only. Maybe two trips?"
ACTION  Introduce a blocker: a white pawn on d6.
ROOK    "Uh-oh, my own pawn is in the way. I can't jump over friends!"
INTERACT (Practise) Star Collector: 3 stars, rook must collect all in ≤ N moves.
         Star rating = moves used vs optimal.
INTERACT (Check)  3 questions: "Which squares can the Rook reach?" (tap all) /
         "Can the Rook get here in ONE move?" (yes/no) / "Fewest moves to the star?"
REWARD  ⭐⭐⭐, Rook badge, Tower Town flag raised on map.
```

---

## 4.11 Lesson 2.9 — "The Leaping Knight"

```
SCENE   Leaping Hills. Knight (Sparky) on e4, bouncing on the spot.
SPARKY  "Hee-hee! I'm Sparky! I never walk straight — I JUMP!"
ACTION  Sparky hops: e4 → e5 → e6 (two steps, footprint trail), then turns → f6.
        The trail glows as a big letter "L".
SPARKY  "Two steps, then one to the side. That makes an L!"
ACTION  Repeat in all 8 directions; the 8 landing squares bloom as flowers.
PIP     "Look! It makes a flower all around him!"
SPARKY  "And here's my magic trick: watch my landing square colour…"
ACTION  Board dims; e4 is light; all 8 flowers are on dark squares. Sparky winks.
SPARKY  "I always jump to the OTHER colour!"
ACTION  Pawns fill the squares around Sparky. He leaps clean over them, with a big arc and a "boing".
SPARKY  "And nobody can block me — I fly right over!"

INTERACT (Try)   Tap any flower square to jump. (all 8 accepted)
INTERACT (Try)   Knight's Quest: Sparky starts on g1, carrot on f7. Optimal route = 3 jumps
                 (e.g. g1→f3→g5→f7); stars awarded for 3 / 4 / 5+ jumps.
  ✘ RETRY   (non-L tap) Sparky trips comically, giggles: "That's not my L! Two, then one!"
             Ghost-L appears from Sparky as hint level 2.
ACTION  Sparky in corner a1 looks sad, only 2 flowers.
SPARKY  "In the corner I only have two jumps… I feel dim! A knight on the rim is dim!"
INTERACT (Practise) 4 quests with increasing distance; one includes enemy-attacked squares to avoid.
INTERACT (Check)  "Tap ALL the squares Sparky can jump to" (from d4) / "Can Sparky reach the light square in ONE jump?"
REWARD  ⭐⭐⭐ + sticker "Horse Whisperer".
```
**[AC] note:** Coach Nova explains the knight as the "non-linear piece", shows the forking geometry in advance, and mentions the knight's tour as an optional challenge.

---

## 4.12 Lesson 2.11–2.12 — "Pip's March" and "Pawns Fight Sideways"

```
SCENE   Pawn Meadows. Only white pawns on rank 2, Pip on e2. A finish line glows on rank 8.
PIP     "This is my favourite lesson — because it's about ME!"
PIP     "Pawns march forward one step at a time. Never backwards — we're brave!"
ACTION  Pip steps e2→e3. Tries to step back; an invisible wall goes "bonk". Pip laughs.
PIP     "But on my very FIRST step, I can take a big jump of two!"
ACTION  Another pawn (d2) jumps d2→d4 with a "whoosh".
INTERACT (Try) Move the c-pawn two squares. Then try to move it two again → blocked, explanation.
ACTION  Black pawn appears on e4, directly in front of Pip (on e3).
PIP     "Oh no! Someone's in front of me. I can't push him and I can't capture him straight ahead…"
ACTION  Pip bumps, nothing happens. "I'm stuck!"
[Lesson 2.12 continues]
PIP     "But pawns have a secret: we fight SIDEWAYS — diagonally forward!"
ACTION  Black knight appears on f4. Pip slashes diagonally (cartoon swoosh), captures; knight
        bows politely and walks off-board to the "bench". [LK: no violence, pieces 'go home']
INTERACT Capture puzzles: 4 positions; one includes a piece straight ahead (trap question).
  ✘ RETRY  (tries to capture straight ahead) PIP: "Remember: we march straight, but fight diagonally!"
ACTION  Finale: unlock Pawn Wars mini-game. Pip looks at rank 8, sighs dreamily.
PIP     "One day, I'll reach the other side…"
```

---

## 4.13 Lesson 3.2 — "Run, Capture, Block" (escaping check)

```
SCENE   Royal Castle throne room. White King Bram on e1, Black Rook slides to e8 with a dramatic
        drum roll; a red laser line connects rook to king. King's crown flashes red.
KING    "Eek! CHECK! I'm in danger!"
PIP     "When the King is in check, we MUST save him right away. There are three ways!"
ACTION  Three big icons drop in: 🏃 RUN  ⚔ CAPTURE  🛡 BLOCK
PIP     "Number one: RUN! Move the King to a safe square."
ACTION  Safe squares glow green, attacked squares red (e2 red: still on the laser line).
INTERACT Move the King to safety.  ✘ (onto e2) King: "Still on the laser! Owie!" — red flash, undo.
PIP     "Number two: CAPTURE the attacker!"
ACTION  Reset; add a white Bishop on h5. It can reach e8 along the diagonal h5–g6–f7–e8.
INTERACT Capture the checking piece.
ACTION  Reset: Black Rook e8 checks the White King on e1 again. White now also has a Knight on c3 and a Bishop on f1.
PIP     "Number three: BLOCK! Put someone in the way, like a shield."
INTERACT Drag a piece onto the laser line (multiple correct squares).
ACTION  Shield animation; laser stops at the blocker.
PIP     "Run, Capture, Block! Say it with me!"  (chant + clap SFX; LK: tap along)

INTERACT (Practise) 6 positions: child must pick WHICH method(s) work, then play it.
         Includes: knight check (can't block!) and double check (only RUN works).
NOVA [AC] "Double check: two attackers. You can't capture or block both — the king must move."
INTERACT (Check) 3 positions, find a legal escape.
REWARD  ⭐⭐⭐ + "Royal Bodyguard" badge.
```

---

## 4.14 Lesson 3.4 & 3.6 — "Checkmate: The Winning Trap" / "Stalemate: The Sneaky Tie"

```
SCENE   Black King h8, white Queen g7 protected by white King f6. (Simple mate.)
PIP     "The Black King is in check… Can he RUN? Let's look."
ACTION  Each of the King's neighbour squares lights red one-by-one with a 'nope' buzz.
PIP     "Can he CAPTURE the Queen? … No — our King protects her!"
ACTION  Protection line King→Queen glows gold.
PIP     "Can anyone BLOCK? … No! No escape! That's CHECKMATE!"
ACTION  Black King gently tips over; golden fireworks; crowd cheer.

[3.6 — Stalemate]
SCENE   Black King h8; white Queen on g6 (NOT check), white King far away; Black to move.
PIP     "Black's turn. Is the King in check? … No!"
ACTION  King tries each square — all red. Other black pieces: none.
PIP     "He's not in danger, but he can't move anywhere. That's STALEMATE. It's a tie!"
KING BRAM "A TIE?! But we were winning!"
PIP     "That's why we always leave the enemy King a little square to breathe — 
         until we're ready for checkmate."
INTERACT Mini-game "Mate or Stalemate?": swipe each 3D card left (Mate) or right (Stalemate),
         8 cards, then "Make it mate": find the move that mates instead of stalemating.
```

---

## 4.15 Lesson 3.8 — "The King's Secret Door" (castling)

```
SCENE   Night at Royal Castle. King on e1, Rook on h1, pieces between them.
KING    "I feel so… exposed in the middle. If only I had somewhere safe to hide…"
ROOK    "Psst, Your Majesty! Use the secret door!"
PIP     "Castling! The King's special move. First, clear the path."
INTERACT Move the knight (g1) and bishop (f1) out of the way (guided).
ACTION  A glowing secret-door arch appears over f1–g1.
PIP     "Now the King takes TWO steps toward the Rook… and the Rook jumps over him!"
INTERACT Drag the King e1→g1 (2 squares). Rook auto-hops h1→f1 with a "whoosh-clunk".
ACTION  A castle-wall shield rises around the King; King sighs happily.
PIP     "That's castling short, on the King's side. There's a long one too!"
ACTION  Show queenside: King e1→c1, Rook a1→d1.

PIP     "But the secret door is locked if…"
ACTION  Traffic-light checklist slides in. Each rule is demonstrated with a mini-scene:
        🔒 The King has moved before         (footprints behind the King)
        🔒 That Rook has moved before         (footprints behind the Rook)
        🔒 Someone is in the way              (piece blocks the path)
        🔒 The King is in check               (red laser on King)
        🔒 The King would walk THROUGH danger (red laser crossing f1)
        🔒 The King would land IN danger      (red laser on g1)
INTERACT (Practise) 6 positions: "Can White castle? Which side?" Child taps 🔓 Kingside /
         🔓 Queenside / 🔒 Neither. Includes the tricky case: only b1 attacked → queenside OK.
NOVA [AC] "Over-the-board tip: touch the King first. Touch the Rook first and you've committed to a rook move."
REWARD  ⭐⭐⭐ + "Castle Architect" badge.
```

---

## 4.16 Lesson 3.9 — "Pip's Big Dream" (promotion) — emotional milestone

```
SCENE   Pawn Meadows at golden hour. Pip on e7. Rank 8 glows with a rainbow.
PIP     "This is it… one more step. Will you help me?"
INTERACT Move Pip e7→e8. Slow motion; orchestral swell.
ACTION  Pip spins in a column of light; four silhouettes appear: Queen, Rook, Bishop, Knight.
QUEEN STELLA "Brave pawn, you've crossed the whole board. Choose who you will become!"
PIP     "I can become a Queen, a Rook, a Bishop or a Knight! Not a King — there's only one."
INTERACT Child picks. (Any choice is celebrated; LK: Queen recommended with sparkle.)
ACTION  Transformation; Pip-Queen keeps Pip's eyes (continuity!). Fireworks.
PIP     "I DID IT! And you know what? ANY pawn can do this — even if we already have a Queen!"
ACTION  Second pawn promotes → two Queens high-five.
INTERACT (Practise) 4 promotion puzzles; [EX/AC] includes one where a Knight promotion gives check
         and wins, and one where a Queen would stalemate.
REWARD  Special golden sticker "Dream Come True"; Pip becomes available as a Queen skin.
        Story beat: Pip returns as a pawn in Level 4 — "Every game, a new journey!"
```

---

## 4.17 Lesson 3.10 — "The Ghost Pawn" (en passant)

```
SCENE   White pawn on e5 (5th rank). Black pawn on d7.
PIP     "Watch this sneaky move…"
ACTION  Black pawn jumps d7→d5, landing right beside e5. A translucent GHOST pawn stays on d6.
PIP     "That pawn tried to run past me with a big jump! But I can catch its ghost!"
INTERACT Capture the ghost: move e5→d6. The real pawn on d5 vanishes in a puff.
PIP     "That's called *en passant* — French for 'in passing'!"
ACTION  Repeat scene; this time the child is told to make another move first. The ghost fades with
        a "poof" and a clock-tick sound.
PIP     "The ghost only stays for ONE turn. Now or never!"
INTERACT (Practise) 6 yes/no positions ("Can White capture en passant?"), 3 of them tricky:
         pawn moved only one square; pawn moved two squares, but not on the last move; pawn not beside it.
REWARD  ⭐⭐⭐ + "Ghost Catcher" badge.
```

---

## 4.18 Lesson 3.14 — "Game Points: Win, Draw, Lose" (Pip)

**Objective:** the child knows win = 1, draw = ½, loss = 0, can read 1-0 / 0-1 / ½-½, can add up a small
tournament table, and doesn't confuse piece points with game points. **Duration:** about 5 min.

```
SCENE   A tiny tournament hall. Three tables, a big scoreboard with empty coin slots.
PIP     "When a game ends, the players get points! Let's see how."
ACTION  Table 1: White checkmates Black. A whole gold coin drops into White's slot. "Clink!"
PIP     "A win gets ONE whole point!"
ACTION  Table 2: a draw. One coin splits into two halves; each player gets a half.
PIP     "A tie gets HALF a point each."
ACTION  Table 3: the losing player gets an empty plate, then a little star sticker that says "I learned something".
PIP     "A loss gets zero points. But every game teaches you something!"
INTERACT (Pick one) "White won. How do we write it?"  1-0 · 0-1 · ½-½
  ✔ SUCCESS  "Yes! White's number comes first."
  ✘ RETRY    "The first number is White's points, the second is Black's. Who won?"
INTERACT (Pick one) "It was a tie. How do we write it?"  → ½-½

ACTION  A mini tournament: Amy, Ben and Cara each play the other two once.
        Amy beats Ben. Ben and Cara draw. Cara beats Amy.
INTERACT (Score Keeper) Drag the coins into each player's row.
        Amy = 1, Ben = ½, Cara = 1½.
PIP     "3 games, so 3 points were shared. Who won the tournament?"
INTERACT Tap the winner → Cara. Confetti.

PIP     "Oh! I captured a queen, so I get 9 points in the tournament, right?"
INTERACT (Spot Pip's mistake) 👍 / 👎
  ✔ SUCCESS  👎 → PIP: "Right! Piece points help me choose good moves. Tournament points only come from
             winning, drawing or losing the game."
INTERACT (Check) 5 items: write a result, add up a 3-player table, win/draw/loss values, piece vs game points.
REWARD  ⭐⭐⭐ + sticker "Score Keeper". Unlocks the mini-game "Score Keeper".
```

**[AC] variant:** Coach Nova adds forfeits (+/−), half-point and full-point byes, and shows a real crosstable.

---

## 4.19 Lesson 5.3 — "Forks: the Royal Fork and the Family Fork" (Explorers / Academy)

```
SCENE   Tactics Jungle. FEN r3k3/pp3ppp/8/1N6/8/8/PPP2PPP/6K1 w - - 0 1
        (White: Kg1, Nb5, pawns a2 b2 c2 f2 g2 h2. Black: Ke8, Ra8, pawns a7 b7 f7 g7 h7.)
        White to move: Nc7+ is a royal fork of King and Rook; nothing can capture the knight on c7.
CAPTAIN ROOK "A fork attacks TWO things at once — like a fork with two prongs picking up two peas!"
ACTION  Knight jumps to c7; two red attack-lines spring to King and Rook; fork prongs graphic.
CAPTAIN ROOK "The King must escape check… and then — snap! — we take the Rook."
INTERACT Child plays the follow-up capture.
NOVA [AC] "Forks work best with CHECK, because the opponent has no time to save both. Look for
          'loose' pieces and the king's position, then ask: which square attacks both?"
INTERACT Fork Finder: tap all squares where the knight would fork two targets.
INTERACT Puzzle set 'Forks' (adaptive, 8 puzzles; rating-matched).
INTERACT Reflection [AC]: "What was the clue in that position?" (choose: loose piece / king on same colour / both on knight-distance)
REWARD  XP + badge progress "Fork Master I/II/III".
```

---

## 4.20 Lesson 6.1 — "Queen + King vs King: the Box Method"

```
SCENE   Endgame Mountains. White Ke1, Qd1; Black Ke5. Coloured fence shows the 'box' the
        Black king is limited to by the queen.
NOVA/PIP "The Queen builds a box around the enemy King. Every move, we make the box smaller."
ACTION  Queen move shrinks the box (fence slides in); box area number decreases.
RULE OF THUMB (on screen): 1) Shrink the box with a knight's-move distance from the King.
                           2) Never leave the King zero squares → stalemate alarm!
                           3) When he's on the edge, bring YOUR King to help.
                           4) Deliver mate on the edge.
INTERACT Child plays the full technique vs bot; stalemate detector gives an early warning
         ("Careful! He'd have no moves!") for LK/EX, no warning for AC.
CHECK    Mate within 15 moves, from 3 random positions.
REWARD   Mountain badge; Boss gate progress.
```

---

## 4.21 Lesson 7.1 — "Opening Principles in Depth" (Academy voice)

```
SCENE    Opening Harbour; realistic board, Coach Nova at a desk with a demo board.
NOVA     "The opening is a race: get your pieces into the game, claim the centre, and get your king safe."
ACTION   Heat map shows how many squares each side controls; numbers update as moves are played.
NOVA     "Five principles:
          1. Fight for the centre (e4, d4, e5, d5).
          2. Develop knights and bishops before moving the same piece twice.
          3. Castle early.
          4. Don't bring the queen out too early.
          5. Connect your rooks."
INTERACT 'Rate the move': for 8 opening moves, child chooses 👍 developing / 👎 time-wasting, with
         short explanations.
INTERACT Replay a short miniature where one side breaks every principle and gets punished
         (e.g., a classic Légal-style trap). Child finds the punishing move.
REWARD   XP; unlocks Repertoire Builder.
```

---

## 4.22 Lesson 10.10 — "Tournament Tables and Tiebreaks" (Nova)

**Objective:** read a crosstable, calculate the main FIDE tiebreaks, and explain why round robins and Swiss events use different ones. Worked examples follow the rules reference (2.12a).

```
SCENE   A tournament hall at the end of the last round. Two players are tied on the final scoreboard.
NOVA    "Same score, but only one trophy for second place. Tiebreaks decide. They're announced before
         the event, so everyone knows the rules."
ACTION  A 4-player round-robin crosstable builds row by row (A 1½, B 2, C 1½, D 1).
NOVA    "Check first: 6 games, 6 points shared. Now A and C are tied. Their own game? A draw. Still tied."
NOVA    "Next tiebreak: Sonneborn-Berger. Add the scores of the players you beat, plus half the
         scores of the players you drew with."
INTERACT (Calculate) "A beat B and drew with C. What's A's Sonneborn-Berger?"  number pad
  ✔ SUCCESS  "2 + ¾ = 2¾. Exactly."
  ✘ RETRY    Hint 1: "What did B score?" Hint 2: "Half of C's 1½ is ¾."
INTERACT (Calculate) C's Sonneborn-Berger → 1¾. "So who's second?" → A.
NOVA    "Why not Buchholz here? In a round robin everyone plays the same opponents, so it's always equal."

ACTION  Switch to a Swiss event. One player's opponents finished on 3, 2½, 1, 4 and 3.
NOVA    "In a Swiss, Buchholz adds up your opponents' scores: it rewards a tougher path."
INTERACT (Calculate) Buchholz → 13½; Cut-1 → 12½; Median → 8½.
INTERACT (Calculate) Progressive score for W, L, W, D, W → running totals 1, 1, 2, 2½, 3½ → 10.
NOVA    "Team events count match points too: at the Olympiad a match win is 2, a drawn match 1."
INTERACT (Tiebreak Detective) Three tied players and a stated tiebreak order: rank them.
INTERACT (Check) 5 items across direct encounter, Buchholz variants, Sonneborn-Berger and progressive score.
REWARD  XP + badge "Tiebreak Detective".
```

---

## 4.23 Lesson 10.11 — "How Ratings Work: Calculating Elo Points" (Nova)

**Objective:** use the FIDE expected-score table and K-factor to calculate a rating change, and know that FIDE, national and online ratings are different scales.

```
SCENE   Nova's desk with a slider: "Rating difference".
NOVA    "Your rating predicts your score. If you're 100 points higher, you're expected to score
         0.64 per game. That number comes from FIDE's official table."
INTERACT Move the slider (0, 100, 200, 300, 400) and watch the expected score: 0.50, 0.64, 0.76, 0.85, 0.92.
NOVA    "After the game: change = K × (your score − expected score)."
ACTION  K-factor cards: K 40 (new players and juniors under 2300), K 20 (below 2400), K 10 (2400 and up).
NOVA    "Example: you're 1500, a junior, so K is 40. Your opponent is 1600, so your expected score is 0.36."
INTERACT (Rating Predictor) "You win. Calculate the change."  → 40 × (1 − 0.36) = +25.6
INTERACT (Calculate) Draw → +5.6. Loss → −14.4.
NOVA    "Beat a stronger player: big gain. Lose to a weaker one: bigger drop. Fair, right?"
NOVA    "Careful: online sites and national federations use different systems. A 1500 online isn't a FIDE 1500."
INTERACT (Pick one) "Which number is your FIDE rating?" Choose among an app practice rating, an online rating and a FIDE card.
INTERACT (Check) 5 items: expected score, K-factor choice, three rating changes.
REWARD  XP + badge "Rating Mathematician". Unlocks the Academy rating calculator.
```

Lesson 10.12 ("Performance Rating, First Ratings and Norms") follows the same pattern, using the dp table and the 6/9 example from the rules reference (2.12a.4).

---

## 4.24 Boss Battle script template

```
SCENE    Kingdom gate. Boss character appears with fanfare (friendly-rival tone, never scary for LK).
BOSS     "To pass my gate, show me what you've learned!"
STRUCTURE 3 rounds (each ≤ 2 min):
          Round 1 – Recall (quick questions in 3D)
          Round 2 – Apply (puzzles/mini-game)
          Round 3 – Play (short game or endgame vs boss bot)
RULES    3 hearts; losing all hearts → "Practice Camp" recommends 2 targeted lessons, then retry.
         (LK: unlimited hearts, boss "gets tired" after enough correct answers.)
VICTORY  Boss bows, gate opens, map camera flies to the next kingdom; certificate + parent notification.
```

## 4.25 Voice-over and localisation notes

- Record the two guide voice sets (Pip, Nova) plus the shared supporting cast. Including wrong-answer feedback for each error type, three explanation styles per concept, boss and bot lines, and scenario-playbook lines, the full curriculum needs an estimated **6,000–8,000 recorded lines per language** (re-estimate once Levels 1–3 are scripted).
- Dynamic text (square names, AI explanations, library explanations) uses **one text-to-speech voice per guide**, designed to sound close to the recorded guide and always marked as Pip's or Nova's "reading voice".
- Mouth movements (visemes) for every recorded line are generated automatically from the audio (for example with the open-source Rhubarb Lip Sync tool) and checked by the animator.
- Keep lines under 12 words for the Little Knights track, and pause for interaction. The scripts in this document are drafts written for readability: before recording, every LK line longer than 12 words is split into shorter lines with pauses.
- Launch languages: **English, Malayalam, Hindi and Arabic** (Arabic with a right-to-left UI; the board is never mirrored). Later: for example Urdu, Tamil, Spanish, French. Voice and language rules for every screen are in [document 16](16-voice-assistant-and-languages.md).
- Piece names follow each language's chess terminology. Algebraic piece letters are localised (for example, Spanish uses R=Rey, D=Dama), with an option to show the international letters.
