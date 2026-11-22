# 16. Voice Assistant on Every Screen, in Four Languages

**Requirement:** every screen has a voice assistant that guides the child. It works in **English, Malayalam,
Hindi and Arabic** from the first release, with more languages later.

> ⚠️ All Malayalam, Hindi and Arabic text in this document is a **draft**. Every line and every chess term must be
> reviewed by native-speaking chess coaches and children's-media writers before recording.

---

## 16.1 The voice assistant: what it does everywhere

The assistant is the guide character for the child's track: **Pip** (ages 5–10) or **Coach Nova** (11–15). It is one
reusable component that every screen uses in the same way.

| # | Behaviour | Detail |
|---|---|---|
| 1 | **Speaks on arrival** | Each screen has an *entry line* that says what this screen is and what to do next. Full line on the first visit; a short version afterwards; silent after the 5th visit unless the child seems stuck |
| 2 | **🔊 Say it again** | A speaker button on every screen repeats the last instruction, slower |
| 3 | **Long-press anything** | Holding any button, piece or square for half a second speaks its name and what it does ("This is the Play door. Tap it to play a game!") |
| 4 | **❓ Help** | Explains the screen in a *different* way (document 11, 11.6), not the same words again |
| 5 | **Idle prompts** | After 15–20 s of no action: a gentle reminder; after 45–60 s: a fresh explanation (document 11, 11.7) |
| 6 | **Feedback** | Every right or wrong action gets a spoken reaction with the reason |
| 7 | **Subtitles** | On by default for ages 8+, off for 5–7 (unless sound is off). Always in the same language as the voice |
| 8 | **Voice commands** (optional) | With on-device speech recognition, a parent can turn on spoken commands: "Continue", "Help", "Again", "Home", and, in games, piece names and squares ("knight to f3"). Only offered in a language where on-device recognition is available on that device |
| 9 | **Speed and volume** | Slow / normal speed; separate volume for voice, music and sound effects |
| 10 | **Never talks over itself** | A new line interrupts the old one cleanly; music ducks while the voice speaks |

**Who gets which voice behaviour:**

| Area | Voice behaviour |
|---|---|
| Child screens (A–G) | Full assistant: speaks on arrival, long-press, help, idle prompts, feedback |
| Parent hub (H) | **🔊 Read this page** button and spoken explanations of each setting, in all four languages, because parents may not read the app's other languages comfortably |
| Teacher mode (I) | 🔊 Read-aloud for every page and instruction; projector mode speaks questions aloud to the class |
| Internal tools (J) | No voice (staff tools) |

---

## 16.2 Languages at launch

| Language | Script and direction | Voice style | Notes |
|---|---|---|---|
| **English** | Latin, left to right | Neutral international English | Source language for scripts |
| **Malayalam** (മലയാളം) | Malayalam script, left to right | Standard Malayalam, simple words for young children | Long words: UI allows about 40% more text width |
| **Hindi** (हिन्दी) | Devanagari, left to right | Simple standard Hindi; common English chess words are allowed where children use them | |
| **Arabic** (العربية) | Arabic script, **right to left** | Simplified Modern Standard Arabic, as used in children's TV; a Gulf-dialect version can be added later | UI mirrored; the chessboard is **never** mirrored |

- **Per-profile language:** each child profile has its own language, so siblings can learn in different languages on one device.
- **Two-language chess words (optional):** in Malayalam, Hindi and Arabic, the guide can add the English chess term after the local one ("शह, in English *check*"), because tournaments and books often use English terms and notation.
- **Fonts:** Noto Sans Malayalam, Noto Sans Devanagari and Noto Naskh Arabic (open font licence), plus the Latin UI font. Large sizes for young children.
- **Numbers in the UI:** Western digits by default; Arabic users can choose Eastern Arabic digits (٠١٢٣) for UI text. Board coordinates always stay a–h and 1–8, as in tournaments everywhere.

---

## 16.3 How squares and moves are spoken

| Item | Rule | Example |
|---|---|---|
| File letters (a–h) | Always the **English letter name**, as used in tournaments in all four regions | "e" |
| Rank numbers (1–8) | Ages 5–7: in the child's language. Ages 8+: the child's language or English (setting). Academy defaults to English, as in tournaments | Hindi: "ई चार" or "e four" |
| Picture alphabet (ages 5–7) | Each file lane keeps the same picture in every language, but the *spoken* word is in the child's language. The Latin letter is shown next to the picture | Lane "a": 🍎 = "apple" / "ആപ്പിൾ" / "सेब" / "تفاحة" |
| Piece names | The local chess term (16.4), with the English term optional | Hindi: "घोड़ा (knight)" |
| Moves in notation | Spoken as piece + square in the child's language ("घोड़ा f3 पर"), shown with international letters (Nf3). PGN export always uses English letters | |

---

## 16.4 Chess terms by language (draft, to be confirmed)

Chess vocabulary varies by region. Where a traditional word and a commonly used English loanword both exist, coaches choose one per language and use it consistently in every line.

| English | Hindi | Malayalam | Arabic |
|---|---|---|---|
| Chess | शतरंज | ചെസ്സ് / ചതുരംഗം | الشطرنج |
| King | राजा | രാജാവ് | الملك |
| Queen | रानी / वज़ीर | റാണി / മന്ത്രി (confirm) | الوزير |
| Rook | हाथी (common), रूक (loanword) | റൂക്ക് (loanword; traditional term to confirm) | الرخ / القلعة |
| Bishop | ऊँट (common), बिशप (loanword) | ബിഷപ്പ് (loanword; traditional term to confirm) | الفيل |
| Knight | घोड़ा | കുതിര | الحصان |
| Pawn | प्यादा | കാലാൾ (confirm) / പോൺ | البيدق / الجندي |
| Check | शह | ചെക്ക് | كش ملك |
| Checkmate | शह और मात | ചെക്ക്മേറ്റ് | كش مات |
| Stalemate | स्टेलमेट (confirm local term) | സ്റ്റെയിൽമേറ്റ് | (confirm local term) |
| Castling | कैसलिंग | കാസ്‌ലിംഗ് | التبييت |
| Promotion | प्रमोशन | പ്രൊമോഷൻ | الترقية |
| En passant | एन पासां | ആൻ പസാന്ത് | الأخذ في المرور (confirm) |

Characters' names stay the same in every language (Pip, Nova, Sparky…), written in each script: पिप / പിപ് / بيب.

**Sample lines (drafts):**

| Moment | English | Hindi | Malayalam | Arabic |
|---|---|---|---|---|
| First screen | "Hi! I'm Pip! Tap the bell!" | "नमस्ते! मैं पिप हूँ! घंटी को छुओ!" | "ഹായ്! ഞാൻ പിപ് ആണ്! മണിയിൽ തൊടൂ!" | "مرحبًا! أنا بيب! المس الجرس!" |
| Check | "Check! Run, capture or block!" | "शह! भागो, पकड़ो या रोको!" | "ചെക്ക്! ഓടൂ, പിടിക്കൂ, അല്ലെങ്കിൽ തടയൂ!" | "كش ملك! اهرب أو التقط أو احجب!" |
| Well done | "Great thinking!" | "बहुत बढ़िया सोचा!" | "നന്നായി ചിന്തിച്ചു!" | "تفكير رائع!" |

---

## 16.5 What the assistant says on every screen

Entry lines are shown in English; each is written and recorded in all four languages. "Short" is the version for repeat visits.

### A. First launch and profiles
| Screen | Entry line | Short |
|---|---|---|
| A0 Language picker (new) | "Tap the friend who talks like you!" (each button speaks its own language) | — |
| A1 Welcome | "Shh… the pieces are sleeping. Let's wake them!" | — |
| A2 Sound check | "Did you hear the bell? Tap the thumbs-up!" | — |
| A3 Age picker | "How big are you? Tap the picture… now tap your cake!" | — |
| A4 Avatar picker | "Pick your face! This will be you." | — |
| A5 Do you know chess? | "Do you already know how chess pieces move?" | — |
| A6 Placement quest | "Let's play a quick game so I know where to start!" | "Quest time!" |
| A7 Who's playing? | "Who's playing today? Tap your face!" | "Tap your face!" |
| A8 Parent setup (new) | (Parent voice) "Welcome! Let's set up your child's learning in two minutes." | — |

### B. Home
| Screen | Entry line | Short |
|---|---|---|
| B1 Home | "Ready for today's adventure? Tap the big play button!" | "Tap play!" |
| B2 Helpers | Long-press each: "Help", "Show me again", "Go home" | — |
| B3 Grown-ups corner | "This part is for grown-ups." | — |
| B4 Academy home (new, 11–15) | Nova: "Here's today's training plan and your progress." | "Today's plan is ready." |

### C. Learn
| Screen | Entry line | Short |
|---|---|---|
| C1 Adventure Map | "This is our map! The glowing path shows where to go next." | "Follow the glow!" |
| C2 Kingdom view | "Welcome to [kingdom]! Each stop is a new lesson." | "Next stop!" |
| C3 Lesson player | Scripted lines (document 4), with a question every 30–60 s | — |
| C4 Remember? | "Quick! Do you remember this one?" | "Remember?" |
| C5 Prove it! | "Think you know this? Show me, and you can skip ahead!" | — |
| C6 Lesson complete | "You did it! Look at your stars!" | — |
| C7 Boss Battle | Boss intro line, then round instructions | — |
| C8 Practice Camp | "Let's practise two little things, then try again. You can do it!" | — |
| C9 Certificate | "You finished [kingdom]! You're a [title] now!" | — |
| C10 Review Island (new) | "Before the next kingdom, let's mix up everything you know!" | — |
| C11 Training Plan (new) | Nova: "This week's plan: [items]. Let's start with the first one." | — |

### D. Practise
| Screen | Entry line | Short |
|---|---|---|
| D1 Practise hub | "What do you want to practise? Games, puzzles or your oops moments?" | — |
| D2 Mini-games library | "Pick a game! Hold a picture to hear about it." | — |
| D3–D4 Each mini-game | Its rules in two short sentences, then "Ready? Go!" | "Ready? Go!" |
| D5 Puzzle Gym | "Puzzle time! Find the best move." | — |
| D6 Daily Puzzle | "Here's today's special puzzle!" | — |
| D7 Oops Replays | "Remember this game? Let's find a better move together." | — |
| D8 Review Queue | "These need a little practice. Let's keep them strong!" | — |
| D9 Trainers | Trainer-specific instruction | — |
| D10 Repertoire Builder | Nova: "Let's practise your openings. Play your move." | — |
| D11 Real Board Challenge (new) | "Get your real chessboard! Set up the pieces like this." (each piece is named as it lights up) | — |
| D12 Endgame Trainer (new) | "Can you win this from here? I'll play the other side." | — |

### E. Play
| Screen | Entry line | Short |
|---|---|---|
| E1 Play hub | "Who do you want to play? A friend on the computer, or someone next to you?" | — |
| E2 Bot picker | Each bot introduces itself when tapped | — |
| E3 Game setup | "Pick your colour. White moves first!" | — |
| E4 Game screen | Coaching lines by level (document 11, 11.4): checks, warnings, special-move hints, "Your turn!" | "Your turn!" |
| E5 Promotion picker | "You reached the end! Who do you want to become?" | — |
| E6 Game over | Result and reason: "Checkmate! You won!" / "It's a tie, because…" | — |
| E7 Coach's Corner | "Let's look at three important moments." | — |
| E8 Pass-and-play | "Pass the device to your friend. Their turn!" | "Pass it on!" |
| E9 Variants | Variant rules in two sentences, with "This is a practice game" | — |
| E10 Friend games | "Share this code with a grown-up to play a friend." | — |
| E11 Tournament simulator | "Round [n]! Shake hands, start the clock, and good luck!" | — |
| E12 Analysis board | Nova: "Move freely. Ask me about any position." | — |
| E13 AR board | "Point the camera at a table… now tap to place the board!" | — |
| E14 Referee mode (new) | "Playing on a real board? Tell me the moves and I'll be your referee." | — |
| E15 My games (new) | "Here are your games. Tap one to watch it again." | — |
| E16 Rated games, 13+ (new) | Nova: "Rated game. No chat; good luck and have fun." | — |

### F. My Trophies
| Screen | Entry line | Short |
|---|---|---|
| F1 Trophy room | "Look at everything you've won!" | — |
| F2 Collection | "Pick a board or pieces you've earned." | — |
| F3 My progress | "Look how far you've come!" (reads the main progress aloud) | — |
| F4 Hall of Legends | Story narration | — |
| F5 Quests (new) | "Today's quest: [quest]." | — |
| F6 Leaderboards (new) | "Here's how your class is doing this week." | — |
| F7 Friends (new) | "These are your chess friends." | — |

### G. System
| Screen | Entry line |
|---|---|
| G1 Help | A different explanation of the current task |
| G2 Idle and sleep | "Still there? … Zzz… Tap me to wake me up!" |
| G3 Slow down | "Whoa! Let's take a big breath together…" |
| G4 Break / time's up | "Great work! Time for a break. See you soon!" |
| G5 Parent gate | "This part is for grown-ups." |
| G6 Ask a grown-up | "Ask a grown-up to help with this one!" |
| G7 Downloading | "I'm getting the next kingdom ready…" |
| G8 Welcome back | "Welcome back, champion! Let's warm up." |
| G9 What's new | "Guess what's new!" |
| G10 Quick settings | Long-press each setting to hear it |
| G11 Language and voice (new) | "Tap a friend to change my language." Speed: "Slow… or normal?" |
| G12 Unlock (new) | "This kingdom needs a grown-up to unlock it. Let's show them!" |
| G13 Save my progress (new) | "Ask a grown-up to save your progress, so you never lose it!" |

### H. Parent hub (read-aloud)
Every parent screen (H1–H15, including the new login, purchases, help, privacy, downloads, account deletion and web dashboard screens) has a **🔊 Read this page** button and a spoken explanation of each setting, in all four languages, using the guide's reading voice (text-to-speech).

### I. Teacher mode (read-aloud)
Every teacher screen (I1–I11) has read-aloud. In projector mode (I5, I10) the assistant reads each question to the whole class in the class's language.

---

## 16.6 How the voice is produced

| Content | How it's voiced | Languages |
|---|---|---|
| Lesson scripts, entry lines, feedback, character lines | **Recorded** by native-speaking actors (two guide voices + supporting cast per language) | All 4 at launch for Levels 0–3 and all screens; later levels added language by language |
| Dynamic text (square names, scores, explanation library, AI answers) | **Text-to-speech** with one "reading voice" per guide per language, chosen to sound close to the recorded guide | All 4 |
| Parent and teacher read-aloud | Text-to-speech | All 4 |

- **Text-to-speech choice:** platform voices differ by device, and some devices have no Malayalam voice. To keep Pip sounding the same everywhere, library and system lines are synthesised **in advance on our servers** and shipped as audio files; only truly live text (AI answers) is synthesised on demand by our server. The TTS provider is chosen after a listening test with children in each language, and is covered by a data-processing agreement.
- **Speech recognition** for voice commands runs only on the device. Availability differs by language and device (it may be missing for Malayalam on some devices); where it's missing, voice commands are simply not offered and tapping works as always.
- **Lip sync:** mouth shapes are generated from each language's recordings automatically and checked by an animator.
- **Recording volume:** about 6,000–8,000 recorded lines per language for the full curriculum; Levels 0–3 plus all screens (about 2,500–3,000 lines per language) are recorded first.

## 16.7 Live AI in four languages

The live AI coach (document 13) answers in the child's language. Claude handles English, Hindi and Arabic well and also handles Malayalam, but quality must be **measured per language**: the AI evaluation set (13.9) includes about 200 positions per feature *per language*, graded by native-speaking coaches. If a language doesn't reach the quality bar, that language uses only the reviewed library and templates.

## 16.8 Right-to-left (Arabic) rules

- The whole UI is mirrored: menus, back buttons, progress bars, the map's reading direction.
- **The chessboard is never mirrored.** a1 stays at White's bottom-left; file letters run a→h left to right from White's view.
- Arrows on the board follow the real move direction, not the reading direction.
- Mixed text (Arabic sentence + "Nf3") is laid out with proper bidirectional isolation so notation never appears reversed.

## 16.9 Quality checks for every language

1. Native-speaker review of every script line and chess term (16.4) by a chess coach.
2. Reading-level check for subtitles (short, simple words for ages 5–10).
3. Play-tests with children who speak each language, counting adult interventions (target: zero, as in document 11).
4. Layout check for long Malayalam words and right-to-left Arabic on the smallest supported phone.
5. Audio check: every screen has entry lines recorded in all four languages before release (the build fails if one is missing).
