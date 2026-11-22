# 6. 3D Visual, Audio & Interaction Design

## 6.1 Art direction

**Goal:** the warmth of a beautiful wooden chess set on a family table, combined with the magic of an animated film.

| Track | Visual style | Pieces | Board |
|---|---|---|---|
| Little Knights (5–7) | Bright, rounded, toy-like; soft lighting; characters with big expressive eyes | **Story Set:** chunky character pieces with faces, idle animations (blink, bounce, yawn) | Thick wooden board with painted borders and picture labels |
| Explorers (8–10) | Adventure-game style; richer materials; still stylised | **Adventure Set:** stylised Staunton shapes with subtle character details (the knight's mane moves) | Themed boards (forest, ocean, space…) |
| Academy (11–15) | Premium, realistic, calm | **Tournament Set:** realistic Staunton pieces (boxwood and ebony, weighted felt bases) | Walnut and maple tournament board with coordinates; optional marble and glass |

All tracks can switch to **2D top-down mode** with one tap. This is important for learning diagrams and notation, and for low-end devices.

## 6.2 "Real chessboard feel": rendering checklist

- **Physically Based Rendering (PBR) materials:** wood grain with clear-coat varnish, felt, marble, brushed metal.
- **Lighting:** an HDRI image for environment lighting and reflections, plus one warm key light with soft shadows (PCSS or VSM) and a cool fill light.
- **Ambient occlusion** baked into the board; screen-space AO (SSAO/GTAO) on high-end devices.
- **Contact shadows** under the pieces, so they look grounded and heavy.
- **Subtle depth of field** in cinematic moments only (never during play, where clarity matters).
- **Tone mapping** (ACES or AgX) plus a gentle bloom for magical effects such as promotion and checkmate.
- **Wooden table and room** environment around the board, which can be themed (bedroom, castle hall, space station).

## 6.3 Piece motion and physics

| Action | Animation (≤ 300 ms in play mode) | Sound |
|---|---|---|
| Pick up | Piece lifts ~1 cm with a slight tilt; its shadow softens and grows | Soft wood "tock" |
| Slide (rook, bishop, queen) | Glides at a constant speed with ease-in and ease-out | Felt slide |
| Knight | Arched hop over the pieces | "Boing" (LK) / soft wooden tap (AC) |
| Place | Small settle bounce | Satisfying wood-on-wood "clack" |
| Capture | LK: the captured piece bows and walks to the side bench. EX: playful poof. AC: realistic removal to the side tray | Gentle whoosh |
| Check | Red pulse ring under the king; the attack line glows | Alert chime (not scary) |
| Checkmate | The king tips over in slow motion; confetti or fireworks (by track) | Fanfare |
| Castling | The king steps, the rook arcs over; the "secret door" effect for LK | Stone-door rumble |
| Promotion | Column of light; the pawn morphs into the new piece | Orchestral swell |
| Illegal move | The piece springs back to its origin; the reason bubble appears | Soft "bonk" |

Captured pieces are placed neatly beside the board, so the child can always see the material balance.

## 6.4 Camera

- **Default:** a 3/4 view from the player's side (about 45° tilt), like sitting at a real board.
- **Orbit and zoom:** two-finger rotate and pinch, with limits so the child can't get lost; a "home" button resets the view.
- **Auto-flip** when playing Black, and in pass-and-play mode.
- **Cinematic cameras** for lesson hooks, boss intros and checkmates (skippable).
- **Lesson focus cams:** the camera frames the squares that matter in the current step.

## 6.5 Board overlays and teaching visuals

- **Legal move indicators:** dots for empty squares, rings for captures. Shape *and* colour are used, so colour-blind players can tell them apart.
- **Last-move highlight**, selected-piece glow.
- **Arrows and circles:** coaches and Coach Nova can draw them; the child can draw them in the Academy analysis board.
- **Attack heat-map:** squares attacked by each side, for the Safe Square lessons.
- **Danger zones** around the king (red), **safe squares** (green).
- **Path trails:** knight L-trails, rook rails, bishop beams.
- **Ghost pieces:** en passant, hint demonstrations, "what if" previews.
- **Coordinates:** on the board edges (toggle); picture-alphabet for LK.

## 6.6 Augmented reality mode (phase 3)

- **Re-scoped after critique round 2:** iOS WebViews do not support WebXR, and no Capacitor plugin renders the Three.js scene in ARKit. Phase 3 AR therefore starts on **Android only** (WebXR in Chrome / ARCore). iOS AR needs a separate native rendering module and is a later, separately estimated project.
- Place a life-size board on a real table. Kids walk around it, and Pip stands on the table to teach.
- "Shadow board" mode: the app shows the moves while the child plays them on their own physical set.

## 6.7 Interaction design

- **Two ways to move:** tap-tap (select, then target) and drag-and-drop. Both are always supported.
- **Taught, not assumed:** Lesson 1.2 ("Your Magic Board") teaches every board interaction before any chess rule, and its rules table (see [Lesson Scripts](04-lesson-scripts.md)) is the single source of truth for selection behaviour.
- **Large touch targets:** a minimum of 48 dp for buttons. On phones (about 360 dp wide) a full board gives squares of only about 40 dp, and the 3D tilt shrinks the far ranks further, so phones default to a **steep, almost top-down camera** (or 2D), and a tapped square is magnified briefly so small fingers can confirm the target. Tablets keep the 3/4 view.
- **Move confirmation** (optional, Academy) to train careful play; **undo** allowed in practice mode only.
- Input: touch, mouse, keyboard (square navigation with arrow keys + Enter for accessibility), stylus.
- Left-handed layout option (the UI panel can be mirrored).

## 6.8 Audio

- **Voice-over:** professional actors for the two guide voices and the shared supporting cast, per language (adult performers for child voices, with contracts that forbid voice cloning; see [document 15](15-business-legal-compliance.md)); subtitles.
- **Music:** an adaptive soundtrack per kingdom. Calmer during puzzles; it swells for boss fights and celebrations. Separate volume sliders.
- **Sound effects:** recorded with real wooden pieces for authenticity, plus a magical layer for LK and EX.
- **Spatial audio** in AR mode.

## 6.9 Accessibility

- Colour-blind-safe palettes (tested for deuteranopia, protanopia and tritanopia); highlights always use shape *and* colour.
- Reduced motion mode (no camera swoops, simple fades).
- Calm mode (muted effects, no confetti).
- Text: dyslexia-friendly font option, adjustable size; all text voiced.
- Screen reader support in 2D mode (each square is announced: "e4, white knight").
- High-contrast board theme.
- RTL layout support (Arabic, Urdu) without flipping the board itself.

## 6.10 Performance budgets

| Device tier | Target | Settings |
|---|---|---|
| High (recent iPad, flagship phones, desktop) | 60 fps | Full PBR, soft shadows, SSAO, bloom |
| Mid (3–4-year-old tablets) | 60 fps | Baked AO, a single shadow map, no SSAO |
| Low (budget Android, school Chromebooks) | ≥ 30 fps | Simplified materials, no real-time shadows (baked blob shadows), or auto-switch to 2D |

- glTF 2.0 assets compressed with Draco or meshopt; KTX2/Basis textures.
- Each piece set ≤ 15k triangles in total (with LODs); board ≤ 5k triangles.
- Initial download ≤ 25 MB, including a single-threaded "lite" chess engine; each kingdom streams its own asset pack (≤ 15 MB).
- **Total storage budget:** about 250 MB with all kingdoms and one language downloaded; a downloads manager lets parents and schools remove kingdoms or languages. School Chromebooks can use a "stream only" mode.
- **WebGL robustness:** recover automatically from a lost WebGL context (common on iOS under memory pressure); if WebGL2 is missing or keeps failing, switch to the 2D board automatically.
- **Battery saver:** lower frame rate and effects when the battery is low or the device is hot.
- Automatic quality detection on the first launch, plus a manual override.
