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

**The lesson rhythm (every lesson):**
1. **Hook** (≤ 20 s): a story moment or a question.
2. **Watch** (I do): the character demonstrates in 3D.
3. **Try** (we do): a guided move with highlighted hints.
4. **Practise** (you do): 3–6 tasks of increasing difficulty, with hints available.
5. **Check:** 3 quick questions; this is the mastery data.
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
| **Captain Rook** | Co-guide (8–10). A friendly tower-captain, strong and steady | Hearty, a little pirate-ish |
| **Queen Stella** | Appears at milestones; the "goal" Pip dreams of | Kind, regal, encouraging |
| **King Bram** | Comic relief; a slightly nervous, very important king | Fussy and funny ("Careful! I'm VERY important!") |
| **Sparky the Knight** | A jumpy horse who never walks straight | Energetic, giggly |
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
REWARD  ⭐⭐⭐ + sticker "Chess Land Visitor". Map: path to "The Magic Board" lights up.
PIP     "Next time, I'll show you the magic board's secrets!"
```

**[EX] variant:** same scene; Pip's lines are shortened and shown as subtitles. Captain Rook adds:
"Every great general knows the goal first. Trap the enemy king!"
**[AC] variant:** Coach Nova, realistic board, 60-second cinematic: *"Chess is a battle between two armies.
You win by checkmate: attacking the enemy king so it can't escape. Everything we learn serves that goal."*

---

## 4.4 Lesson 1.4 — "Every House Has an Address" (coordinates)

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

## 4.5 Lesson 1.5 — "Build the Army" (setup)

```
SCENE   Empty board; pieces wait in a toy chest beside it.
PIP     "Time to build our army! First — turn the board the right way.
         Light on the right!"
INTERACT Rotate the board (swipe) until the bottom-right corner is light.
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

## 4.6 Lesson 2.1 — "Captain Rook's Straight Roads"

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

## 4.7 Lesson 2.9 — "The Leaping Knight"

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
INTERACT (Check)  "Tap ALL the squares Sparky can jump to" (from d4) / "Can Sparky reach the light square?"
REWARD  ⭐⭐⭐ + sticker "Horse Whisperer".
```
**[AC] note:** Coach Nova explains the knight as the "non-linear piece", shows the forking geometry in advance, and mentions the knight's tour as an optional challenge.

---

## 4.8 Lesson 2.11–2.12 — "Pip's March" and "Pawns Fight Sideways"

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
ACTION  Black knight appears on d4. Pip slashes diagonally (cartoon swoosh), captures; knight
        bows politely and walks off-board to the "bench". [LK: no violence, pieces 'go home']
INTERACT Capture puzzles: 4 positions; one includes a piece straight ahead (trap question).
  ✘ RETRY  (tries to capture straight ahead) PIP: "Remember: we march straight, but fight diagonally!"
ACTION  Finale: unlock Pawn Wars mini-game. Pip looks at rank 8, sighs dreamily.
PIP     "One day, I'll reach the other side…"
```

---

## 4.9 Lesson 3.2 — "Run, Capture, Block" (escaping check)

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
ACTION  Reset; add a white Bishop on h5 — it can reach e8 along the diagonal.
INTERACT Capture the checking piece.
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

## 4.10 Lesson 3.4 & 3.6 — "Checkmate: The Winning Trap" / "Stalemate: The Sneaky Tie"

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

## 4.11 Lesson 3.8 — "The King's Secret Door" (castling)

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

## 4.12 Lesson 3.9 — "Pip's Big Dream" (promotion) — emotional milestone

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

## 4.13 Lesson 3.10 — "The Ghost Pawn" (en passant)

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
         pawn moved only one square; pawn moved two but last turn; pawn not adjacent.
REWARD  ⭐⭐⭐ + "Ghost Catcher" badge.
```

---

## 4.14 Lesson 5.2 — "The Knight Fork" (Explorers / Academy)

```
SCENE   Tactics Jungle. White: Kg1, Nb5, pawns. Black: Ke8, Ra8, pawns. White to move: Nc7+ forks King and Rook.
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

## 4.15 Lesson 6.1 — "Queen + King vs King: the Box Method"

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

## 4.16 Lesson 7.1 — "Opening Principles in Depth" (Academy voice)

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

## 4.17 Boss Battle script template

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

## 4.18 Voice-over and localisation notes

- Record each line in three voice styles (LK, EX, AC) where it differs; about 4,000 lines for the full curriculum.
- Keep lines under 12 words for the Little Knights track, and pause for interaction.
- Launch languages: English and Arabic (right-to-left UI, with board orientation unchanged). Later: Spanish, French, Hindi, Urdu, Mandarin.
- Piece names follow each language's chess terminology. Algebraic piece letters are localised (for example, Spanish uses R=Rey, D=Dama), with an option to show the international letters.
