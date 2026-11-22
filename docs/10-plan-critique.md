# 10. Critique Round 1: What Was Wrong With Our First Plan, and What We Changed

This is an honest review of documents 1–8 against two requirements:
1. **Simple and beginner-friendly.**
2. **Kids learn alone, with no adult guidance:** the app itself must guide, teach and question them.

It also uses the lessons from the [competitor analysis](09-competitor-analysis.md).

## 10.1 Summary of problems found

| # | Problem in the first plan | Why it matters | Severity |
|---|---|---|---|
| 1 | **A parent had to create an account before the child could play** (onboarding in the MVP list) | A child alone can't start the app. This contradicts "learn without adults" | 🔴 High |
| 2 | **Too many places to go** on the home screen (Adventure Map, Puzzle Gym, Play Zone, Coach's Corner, Hall of Legends, AR…) | A 5-year-old gets lost; choice overload | 🔴 High |
| 3 | **The guide mostly *tells*; it rarely *asks*** | Without an adult, the app must check understanding constantly. Questioning was limited to end-of-lesson checks | 🔴 High |
| 4 | **No plan for what happens when things go wrong** (child stuck, idle, tapping randomly, quitting midway, coming back after weeks) | An adult normally handles these moments. Alone, a child just gives up | 🔴 High |
| 5 | **Three full voice tracks** (Little Knights, Explorers, Academy) × 120 lessons × several languages | About 4,000 lines per language. Too expensive, slows content, and the Explorers track is very close to Little Knights | 🟠 Medium |
| 6 | **The hint ladder repeated the same explanation** | If a child didn't understand it the first time, hearing it again rarely helps. They need a *different* explanation | 🟠 Medium |
| 7 | **Difficulty adjusted mainly downwards** | Competitors are criticised for being "too easy". Kids who already know the rules would be bored in Levels 1–3 | 🟠 Medium |
| 8 | **No check that every rule scenario is actually taught and tested** | Coverage relied on the curriculum list. There was no traceability from rules to lessons to questions | 🟠 Medium |
| 9 | **Some words assume reading or adult vocabulary** ("concept", "discrimination", "en passant" before explanation) | Non-readers depend 100% on voice and icons | 🟡 Low |
| 10 | **Mini-games and map are separate from learning** | DragonBox shows that navigation itself can be practice | 🟡 Low |
| 11 | **Free-play games against bots happen without coaching** | Bad habits form when nobody comments. Dr. Wolf shows live coaching works | 🟡 Low |

## 10.2 Changes made

| # | Change | Where |
|---|---|---|
| 1 | **Play first, no account.** The app opens straight into Pip's welcome. Progress is saved on the device with no personal data. A **parent gate** (a simple grown-up check) appears only for settings, cloud sync, purchases and sharing | [11.2](11-self-guided-learning.md#112-first-launch-with-no-adult-present), [07](07-technical-architecture.md), [08](08-roadmap-and-delivery.md) |
| 2 | **One big "Play" button.** The home screen is Pip, a big **▶ Continue my adventure** button, and four small doors: **Learn · Practise · Play · My Trophies**. Extra areas unlock gradually, with Pip introducing each one | [11.3](11-self-guided-learning.md#113-simple-by-design-the-ui-rules) |
| 3 | **The guide asks a question every 30–60 seconds**: predictions, "find it", "spot Pip's mistake", "why?" questions, teach-back. A question bank of 12 question types | [11.4](11-self-guided-learning.md#114-the-guide-that-asks-questions), [11.5](11-self-guided-learning.md#115-question-types) |
| 4 | **Scenario playbook:** 40+ situations (stuck, idle, random tapping, crying-level frustration, too easy, returning after a break, lost game, younger sibling…) each with a defined app response | [11.7](11-self-guided-learning.md#117-scenario-playbook-what-the-app-does-when) |
| 5 | **Two voice sets instead of three.** *Pip* (ages 5–10; Explorers reuse Pip's lines with subtitles, XP and harder practice) and *Coach Nova* (ages 11–15). This cuts voice-over by about a third, with no loss for children | [01](01-product-vision.md), [04](04-lesson-scripts.md) |
| 6 | **"Teach it another way."** Every concept has at least 3 different explanations (story, visual demonstration, rule-of-thumb/mnemonic). Hints rotate between them instead of repeating | [11.6](11-self-guided-learning.md#116-when-the-child-doesnt-understand-teach-it-another-way) |
| 7 | **Difficulty adjusts both ways.** "Too easy? Prove it!" challenge on every lesson lets a child test out in under a minute. Placement quest for anyone who already plays | [11.8](11-self-guided-learning.md#118-adapting-both-ways-too-easy-and-too-hard) |
| 8 | **Rules coverage matrix:** every rule and edge case from document 2 mapped to a lesson, a practice task, a question and a boss check | [11.9](11-self-guided-learning.md#119-rules-coverage-matrix-every-scenario-taught-and-tested) |
| 9 | **Voice-and-icon only for ages 5–7.** Word list rules: one idea per sentence, ≤ 12 words, technical words introduced with a story first ("the ghost-pawn move… grown-ups call it *en passant*") | [11.3](11-self-guided-learning.md#113-simple-by-design-the-ui-rules) |
| 10 | **The map moves like the piece.** In Piece Valley, the child travels the map using the movement of the piece being learned | [09 §9.3](09-competitor-analysis.md#93-the-good-ideas-we-are-adopting), [03](03-curriculum-and-levels.md) |
| 11 | **Coached games.** In practice games the guide gives live tips, warns before blunders (for beginners), offers take-backs with an explanation, and reviews 3 key moments at the end | [11.4](11-self-guided-learning.md#114-the-guide-that-asks-questions) |

## 10.3 What we deliberately kept

- **The 10-level curriculum.** It is long, but it is the path to mastery, and each level is self-contained.
- **3D as the main experience**, with 2D as an option. This is our differentiator; competitors are mostly 2D.
- **Full FIDE rules coverage**, including en passant, castling conditions and every draw rule. Competitors that skip these leave kids confused in real games.
- **No ads, no in-app currency, no chat.**

## 10.4 Open questions for the next critique round

1. Should the youngest track (5–6) use **mini-boards (4×4, 6×6)** for *all* of Level 2, or only the first lesson of each piece? *Needs play-testing.*
2. Is a **microphone answer mode** (the child says "e4" or "knight") worth the privacy cost? Proposal: on-device speech recognition only, off by default, parent-enabled.
3. How much **free play** should be unlocked before Level 3 is finished? Kids want to "play a real game" early. Proposal: unlock coached games against Bumble right after Level 2, with the guide handling check situations.
4. Business model: confirm "Levels 1–3 free forever", so the rules are never behind a paywall.
