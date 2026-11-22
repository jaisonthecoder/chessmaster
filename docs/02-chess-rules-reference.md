# 2. Chess Rules Reference (Knowledge Base)

This is the single source of truth for every rule the app teaches and enforces. It follows the
**FIDE Laws of Chess** (the international rules used in rated tournaments). Each section has three parts:

- **Rule:** the precise rule (used by the rules engine and the content team).
- **Kid version:** how Pip or Coach Nova explains it.
- **Teaching notes:** how the app presents it, and common misconceptions to address.

> Content owners must re-check the official FIDE Laws (handbook.fide.com) every year. FIDE updates
> details, especially on clocks, illegal-move penalties and arbiter procedures. Sections 2.9–2.11 note
> where details depend on the event's regulations.

---

## 2.1 The goal of the game

**Rule.** Two players, White and Black, move in turn. The goal is to **checkmate** the opponent's king:
attack it so that it has no legal way to escape. A game can also be won if the opponent resigns or runs
out of time, and can end in a **draw** (see 2.8).

**Kid version.** "Each team has a king. Protect yours, and trap theirs! When the king is trapped and can't
escape, that's *checkmate* and you win!"

**Teaching notes.** Introduce the *goal* before the pieces, so every lesson has a "why". Kings are
never captured. Many beginners think you win by "taking the king". Show that the game ends one move
earlier, at checkmate.

---

## 2.2 The board

**Rule.**
- 8 × 8 = 64 squares, alternating light and dark.
- Place the board so each player has a **light square in the bottom-right corner** (h1 for White, a8 for Black).
- **Files** are the columns, labelled **a–h** from White's left to right.
- **Ranks** are the rows, numbered **1–8** from White's side.
- **Diagonals** are lines of same-coloured squares that touch at their corners.
- Every square has a name: file + rank (for example, e4).

**Kid version.** "Light on the right! The board is a city with 64 houses. Streets going up are *files*
(a to h), streets going across are *ranks* (1 to 8). Every house has an address, like **e4**."

**Teaching notes.**
- 5–7 year olds: files are shown as coloured lanes with picture labels (apple, ball, cat… for a, b, c…),
  ranks as floors of a building.
- Coordinate games: "Tap the square", "Name the square" and "Coordinate Rush" (timed) for older kids.
- Center squares: d4, e4, d5 and e5 glow during "center control" lessons.

---

## 2.3 Setting up the pieces

**Rule.** Each side has 16 pieces: 1 King, 1 Queen, 2 Rooks, 2 Bishops, 2 Knights, 8 Pawns.

| Square (White) | Piece | Square (Black) |
|---|---|---|
| a1, h1 | Rook | a8, h8 |
| b1, g1 | Knight | b8, g8 |
| c1, f1 | Bishop | c8, f8 |
| d1 | Queen | d8 |
| e1 | King | e8 |
| a2–h2 | Pawns | a7–h7 |

- **The queen goes on her own colour:** the white queen on the light square d1, the black queen on the dark square d8.
- The kings face each other on the e-file. **White always moves first.**

**Kid version.** "Towers in the corners, horses next to them, then the bishops. The Queen loves to match:
she goes on her own colour! The King takes the last spot. The pawns stand in front like a wall."

**Teaching notes.** "Build the Army" drag-and-drop game, where pieces wiggle if placed wrong.
Common mistakes: board rotated (dark square in the corner), and king and queen swapped.

---

## 2.4 How the pieces move

General rules:
- A piece moves to an **empty square** or **captures** an enemy piece by moving onto its square. The captured piece is removed.
- You can never capture your own pieces.
- **No piece except the knight can jump** over other pieces.
- You **must not leave your own king in check** after your move (see 2.6).
- Moving is compulsory. You cannot skip a turn (this is why stalemate and *zugzwang* exist).

### 2.4.1 King ♔
**Rule.** Moves **one square in any direction** (8 directions). It can never move onto a square attacked by an
enemy piece, so the two kings can never stand next to each other. Special move: **castling** (2.5.1).
**Kid version.** "The King is very important but a bit slow. Just one step any way. And he never walks into danger!"
**Teaching notes.** Show "danger squares" in red. Mini-game: *King's Walk* (reach the flag without stepping on attacked squares).

### 2.4.2 Queen ♕
**Rule.** Moves **any number of squares** along a rank, file or diagonal (rook + bishop combined), without jumping.
**Kid version.** "The Queen is the superhero! She zooms in straight lines AND diagonal lines, as far as she wants."
**Teaching notes.** Introduce *after* the rook and bishop ("Rook + Bishop = Queen"). Warn about bringing the queen out too early (Level 4+).

### 2.4.3 Rook ♖
**Rule.** Moves **any number of squares** along a rank or file, without jumping.
**Kid version.** "The Rook is a tower on wheels: straight forward, back, left, right, like a plus sign ➕."
**Teaching notes.** The first piece taught in most curricula, because it is the simplest long-range mover. Mini-game: *Star Collector* (collect stars in the fewest moves).

### 2.4.4 Bishop ♗
**Rule.** Moves **any number of squares** diagonally, without jumping. A bishop **always stays on the same colour** square, so each side has one "light-squared" and one "dark-squared" bishop.
**Kid version.** "The Bishop slides diagonally, like an ✖. He's loyal to his colour and never leaves it!"
**Teaching notes.** Puzzle: "Can the bishop reach the star?" (no, the star is on the wrong colour). This teaches the colour-binding concept.

### 2.4.5 Knight ♘
**Rule.** Moves in an **"L"**: two squares in one direction (rank or file), then one square at a right angle. Equivalently, it goes to the nearest square that is *not* on its own rank, file or diagonal. It **jumps over** any pieces in between. It **always lands on the opposite colour**. It captures only on its landing square.
**Kid version.** "The Knight is the jumpy horse! Two steps, then one step to the side, making an L. Hop over anyone in the way!"
**Teaching notes.** The hardest piece for young kids. Use three methods:
1. *L-shape* with an animated trail.
2. *Colour flip:* the knight always lands on the other colour.
3. *Knight's flower:* from the centre, the 8 targets form a ring around a "skipped" 5×5 box.
Mini-games: *Knight's Quest* (reach targets), *Knight vs Pawns*. Show that a knight in the corner has only 2 moves ("a knight on the rim is dim").

### 2.4.6 Pawn ♙
**Rule.**
- Moves **straight forward one square** to an empty square.
- On its **first move**, may move **two squares** forward if both squares are empty.
- **Captures diagonally forward one square.** It cannot capture straight ahead.
- **Never moves backward.**
- Special moves: **en passant** (2.5.2) and **promotion** (2.5.3).

**Kid version.** "Pawns are little soldiers who only march forward, never back! But they fight sideways,
diagonally. On their very first step they can take a big jump of two."
**Teaching notes.** The most rule-dense piece. Teach in three steps: move, then capture, then first-move double step. Misconception check: "Can the pawn capture the piece directly in front?" (No, it is blocked.) Mini-game: **Pawn Wars** (only pawns; the first to reach the far side wins). This is a classic teaching game.

### Piece values (a guideline, not a rule)

| Pawn | Knight | Bishop | Rook | Queen | King |
|---|---|---|---|---|---|
| 1 | 3 | 3 (often slightly more than a knight) | 5 | 9 | priceless (∞) |

---

## 2.5 Special moves

### 2.5.1 Castling
**Rule.** A move of the king and one rook, counted as **one king move**:
- The king moves **two squares** toward the rook, and the rook jumps to the square the king crossed.
  - **Kingside (short), O-O:** White Ke1→g1, Rh1→f1. Black Ke8→g8, Rh8→f8.
  - **Queenside (long), O-O-O:** White Ke1→c1, Ra1→d1. Black Ke8→c8, Ra8→d8.
- **Castling is not allowed if:**
  1. The king **has already moved** (even if it moved back).
  2. That rook **has already moved**.
  3. There are **any pieces between** the king and that rook.
  4. The king is **currently in check**.
  5. The king would **pass through** a square attacked by the opponent.
  6. The king would **land on** an attacked square (this is true of any move).
- It *is* allowed if the **rook** is attacked, or (when castling queenside) if the rook passes over an attacked square
  (b1 or b8). Only the king's path matters.
- Over the board, **touch the king first** and move it two squares, then move the rook *with the same hand*.
  Touching the rook first means you must move the rook and cannot castle on that turn (touch-move, 2.9).

**Kid version.** "Castling is the King's secret move! He hides in his castle: the King takes two big steps
toward the Rook, and the Rook jumps over him to guard him. But the King can't castle if he's in check,
if he'd walk through danger, or if he or that Rook have moved before."

**Teaching notes.** Use a "secret door" animation. Interactive checklist with a traffic light for each
condition. Practise with a puzzle set: "Can White castle here? Which side?" Include the queenside rook-passes-attacked-b1 case to confuse experts.

### 2.5.2 En passant ("in passing")
**Rule.** If a pawn moves **two squares** from its starting square and lands **right beside** an enemy pawn
(same rank, adjacent file), that enemy pawn may capture it **as if it had moved only one square**. It moves
diagonally to the square the pawn skipped, and the pawn that moved two is removed.
- This is only possible **on the very next move**. Otherwise the right is lost.
- For White, capturing pawns are on the **5th rank**. For Black, on the **4th rank**.
- Like any move, it is illegal if it leaves your own king in check.

**Kid version.** "Sneaky pawns can't run past you! If an enemy pawn jumps two squares to land right next
to your pawn, you can catch it as if it only took one step. But only right away: it's a now-or-never move!"

**Teaching notes.** Show a "ghost pawn" on the skipped square for one turn. The ghost fades away after
the turn to show the now-or-never rule. Quiz: "Is en passant possible here?" with 50% trick positions.

### 2.5.3 Promotion
**Rule.** A pawn that reaches the **last rank** (8th for White, 1st for Black) **must** be exchanged, as part
of the same move, for a **queen, rook, bishop or knight of the same colour**. It cannot become a king or
stay a pawn. The choice does not depend on which pieces were captured, so you can have two or more queens. The
new piece acts immediately (for example, it can give check). Choosing a piece other than a queen is called **underpromotion**.

**Kid version.** "When a brave pawn marches all the way to the other side, it gets a magic upgrade! It can become
a Queen, Rook, Bishop or Knight. Most of the time we pick the Queen!"

**Teaching notes.** This is the **story arc of the whole app**: Pip the Pawn dreams of becoming a Queen. Show a
sparkling transformation animation. Level 6 and higher includes underpromotion puzzles (a knight promotion
with check, or a rook promotion to avoid stalemate).

---

## 2.6 Check

**Rule.** A king is **in check** when it is attacked by one or more enemy pieces. A player in check **must**
get out of check on their next move. There are only three ways:
1. **Move** the king to a safe square (castling is not allowed).
2. **Capture** the checking piece (with the king only if the captured piece is not protected).
3. **Block** by putting a piece between the checker and the king. This is impossible against a knight or pawn, or against adjacent checkers.

In **double check** (two pieces checking at once) **only a king move** works.
You may never make a move that **puts or leaves your own king in check**. For example, a **pinned** piece
can't move off the line between the attacker and its king.

**Kid version.** "*Check!* means 'Your King is in danger!' You MUST save him right now. Remember the three escapes:
**Run, Capture, Block!**"

**Teaching notes.** The "Run, Capture, Block" mnemonic with three icons. Practise with positions where 1, 2 or 3
escapes are possible, and double-check positions to show that only *Run* works. Saying "check" aloud is
**not required** by the rules. Tell older kids this, because many think it is mandatory.

---

## 2.7 Checkmate and stalemate

### Checkmate
**Rule.** The king is **in check** and there is **no legal move** to escape. The game ends immediately and the
checkmating player **wins**.
**Kid version.** "The King is in danger and can't Run, Capture or Block. Checkmate! Game over, you win!"

### Stalemate
**Rule.** The player to move is **not in check** but has **no legal move**. The game is a **draw**.
**Kid version.** "Uh-oh! The King is NOT in danger, but nobody can move. That's *stalemate*, a tie! Be careful:
when you're winning, always leave the enemy King a square to breathe."

**Teaching notes.** Side-by-side 3D comparison: same picture, one with check and one without. *Mate or Stalemate?*
sorting game. Level 6 endgame lessons repeat the stalemate traps in K+Q vs K.

---

## 2.8 How a game ends

### Win
- **Checkmate.**
- **Resignation:** the opponent gives up.
- **Time forfeit:** the opponent's clock runs out (but see the draw exception below).
- The opponent makes repeated illegal moves or breaks rules, according to the competition's penalties (2.9).

### Draw
| Type | Rule | Automatic or claimed |
|---|---|---|
| **Stalemate** | Side to move has no legal move and is not in check | Automatic |
| **Dead position (insufficient material)** | No sequence of legal moves can lead to checkmate. For example: K vs K; K+B vs K; K+N vs K; K+B vs K+B with bishops on the same colour | Automatic |
| **Agreement** | Both players agree to a draw (event rules may restrict this) | By agreement |
| **Threefold repetition** | The same position occurs 3 times with the same player to move and the same castling and en-passant rights (not necessarily consecutively) | Claimed by a player |
| **Fivefold repetition** | The same position occurs 5 times | Automatic |
| **50-move rule** | 50 moves by each player without any pawn move or capture | Claimed by a player |
| **75-move rule** | 75 moves by each player without any pawn move or capture (unless the last move was checkmate) | Automatic |
| **Timeout vs no mating material** | A player's time runs out, but the opponent **cannot checkmate by any legal sequence** (for example, the opponent has a lone king) | Automatic draw |

**Notes.**
- K+N+N vs K is **not** a dead position (mate is *possible* if the defender blunders, even though it can't be forced). It doesn't end automatically.
- In the app's casual games, threefold repetition and the 50-move rule are applied **automatically** for kids under 11,
  with an explanation pop-up. The Academy track teaches *claiming* a draw, as in real tournaments.

---

## 2.9 Over-the-board conduct (tournament rules)

The app teaches these in Level 10 ("Tournament Player") with a role-play "Arbiter Academy".

- **Touch-move:** if you deliberately touch one of your pieces, you must move it (if it has a legal move). If
  you deliberately touch an opponent's piece, you must capture it (if it can be legally captured).
- **"J'adoube" / "I adjust":** say it *before* touching a piece just to straighten it.
- **A move is complete** when you release a piece on a new square (for castling, when the rook is released; for
  promotion, when the new piece is released on the square).
- **Illegal moves:** if an illegal move is noticed, the position is restored and a legal move must be played with
  the same piece if possible. In FIDE-rated play the opponent gets extra time for the first illegal move, and
  a **second illegal move loses the game**. Exact time bonuses differ between standard, rapid and blitz play; check the current Laws.
- **Clock:** press the clock with the same hand that moved the piece.
- **Scoresheet:** in standard (slow) games, players must write every move in algebraic notation (2.10).
- **Fair play:** no electronic devices, no notes, no advice from others, no distracting the opponent.
- **Sportsmanship:** shake hands before and after. Win gracefully, lose gracefully.

**Kid version.** "Touch it, move it! If you only want to fix a piece, say *'I adjust'* first."

---

## 2.10 Chess notation

**Algebraic notation (the FIDE standard):**

| Symbol | Meaning | Example |
|---|---|---|
| K Q R B N | King, Queen, Rook, Bishop, kNight | Nf3 = knight moves to f3 |
| *(none)* | Pawn | e4 = pawn moves to e4 |
| x | Captures | Bxe5, exd5 (pawn captures are named by file) |
| + | Check | Qh5+ |
| # | Checkmate | Qf7# |
| O-O / O-O-O | Kingside / queenside castling | |
| =Q | Promotion | e8=Q |
| e.p. | En passant (optional suffix) | exd6 e.p. |
| Disambiguation | When two identical pieces can reach the square | Nbd2, R1e2 |
| 1-0, 0-1, ½-½ | White wins, Black wins, draw | |

**Annotation symbols** (Academy track): `!` good, `!!` brilliant, `?` mistake, `??` blunder, `!?` interesting,
`?!` dubious.

**Formats used inside the app:** **FEN** (one position as a text string) and **PGN** (a whole game). Kids can
export their games as PGN in the Academy track.

---

## 2.11 Clocks and time controls

| Category (FIDE) | Time per player |
|---|---|
| **Standard (classical)** | 60 minutes or more (for example, 90 min + 30 s per move) |
| **Rapid** | More than 10 and less than 60 minutes (for example, 15 + 10) |
| **Blitz** | 10 minutes or less (for example, 3 + 2) |
| **Bullet** (online only, not a FIDE category) | Under 3 minutes |

- **Increment (Fischer):** seconds added after each move. **Delay (Bronstein/US delay):** the clock waits before counting down.
- For time categories, the total includes 60 × increment (for example, 10 min + 5 s counts as 15 minutes, which is rapid).
- In the app, kids under 11 play **without clocks** by default. Clocks are introduced gently in Level 10.

---

## 2.12 Ratings, titles and the path to mastery

- **Elo rating:** a number measuring playing strength. FIDE publishes official ratings. Beginners start around 1000–1400 when they enter rated play.
- **FIDE titles** (open): Candidate Master (CM, 2200), FIDE Master (FM, 2300), International Master (IM, 2400 plus norms), **Grandmaster (GM, 2500 plus three norms)**.
- **Women's titles:** WCM (2000), WFM (2100), WIM (2200), WGM (2300). Girls may pursue open titles too.
- **Youth pathway:** school and club tournaments, then national age-group championships (U8, U10, U12, U14, U16…), then continental and world youth championships.
- The app's Level 10 explains this pathway, and the parent hub links to national federations and local clubs.
  *Titles are for inspiration: the app never promises outcomes.*

---

## 2.13 Variants used for teaching

| Variant | Purpose |
|---|---|
| **Pawn Wars** (only pawns; first to promote wins) | Pawn movement, captures, races |
| **Mini-boards** (4×4, 5×5, 6×6) | Lower complexity for ages 5–7 |
| **Piece vs Pawns** (for example, a queen vs 8 pawns) | Piece power and coordination |
| **Capture-all** | Captures, without check rules |
| **King of the Hill** (reach the centre) | King safety and centre control (Level 4+ fun mode) |
| **Chess960 / Fischer Random** | Advanced: random back rank (bishops on opposite colours, king between the rooks; 960 setups); castling ends on the same squares as normal. Tests understanding over memorisation |

> The app always labels a variant as a "practice game" so kids never confuse it with real chess.

---

## 2.14 Rules-engine edge cases (QA checklist)

Every case must have an automated test. The rules engine (chess.js) is also validated with *perft* move-count tests.

1. Castling is forbidden when the king passes through an attacked square (f1/g1 or d1/c1).
2. Queenside castling is **allowed** when only b1 (the rook's path) is attacked.
3. Castling rights are lost permanently after a king or rook move, even if it returns. Rights are also lost when the rook is captured on its starting square.
4. En passant is available only on the immediately following move.
5. En passant is illegal if it exposes the king. Example: the king and an enemy rook on the 5th rank with both pawns between them ("horizontal pin").
6. En passant that delivers check or checkmate.
7. Promotion with capture (for example, exd8=Q) and promotion that gives check or mate.
8. Underpromotion to a knight that gives check; underpromotion to avoid stalemate.
9. A pinned piece cannot move off the pin line, but **can still give check** to the enemy king.
10. A king cannot capture a protected piece.
11. Double check: only king moves are legal.
12. Stalemate positions involving pinned pieces.
13. Repetition counting requires identical castling and en-passant rights.
14. The 50-move counter resets on any pawn move or capture.
15. Insufficient material detection, including K+B vs K+B with same-coloured bishops.
16. Timeout with the opponent having only a king is a draw.
17. Two kings can never be adjacent.
18. Multiple queens after promotion; 3D piece pools must support up to 9 queens per side.
