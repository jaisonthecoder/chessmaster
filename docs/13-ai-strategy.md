# 13. AI Strategy: Using AI Efficiently and Safely

## 13.1 The core principle

> **Chess engines decide what is true. Language models decide how to say it to a child.**

A chess engine (Stockfish) and the rules library (chess.js) are fast, free, offline and **always right** about
chess facts: legal moves, best moves, blunders, checkmate. A large language model (LLM) is excellent at explaining
in warm, age-appropriate words, but it can misread a chess position. So:

- **Never** ask the LLM to work out whether a move is legal, what the best move is, or who is winning.
- **Always** compute the facts first with the engine, then give those facts to the LLM to *phrase*.
- **Check** the LLM's answer against the facts before a child sees or hears it.

The second principle is about cost:

> **Pre-generate what you can, cache what repeats, and only call the AI live for what is truly unique.**

---

## 13.2 Three kinds of AI in the app

| Kind | Runs where | Cost per use | Used for |
|---|---|---|---|
| **1. Classic AI** (engines, algorithms, small on-device models) | On the device | Free | Bots, hints, mistake detection, adaptive difficulty, spaced repetition, speech |
| **2. Offline content factory** (LLM in batch, reviewed by people) | Our servers, before release | One-off | Explanation library, question banks, script drafts, translations, quality checks |
| **3. Live AI coach** (LLM in real time) | Our server (AI gateway) | Per call | Explaining the child's *own* game moments, "Why?" answers, "Ask Pip/Nova" questions |

Most of the app's "intelligence" comes from kind 1 and kind 2. Kind 3 is used only where nothing pre-made fits.

---

## 13.3 Classic AI features (on-device, free, works offline)

| Feature | Technique | Where it shows up |
|---|---|---|
| **Bot opponents** | Stockfish (WebAssembly) with personality settings; candidate moves sampled by weight so bots make human-like mistakes. Later, optionally, open human-move models trained on real games (for example, the Maia project; check its licence) | Play Zone, boss battles |
| **Hints and best moves** | Stockfish analysis | Hint ladder, puzzle solutions |
| **Mistake detection** | Evaluation drop + "is the moved piece now capturable?" checks | Blunder warnings, Oops Replays, game review |
| **Tactic detector** | Rule-based detection of forks, pins, skewers, hanging pieces, back-rank weaknesses, using chess.js + engine lines | Explanations ("That's a fork!"), puzzle tagging, "Find it in a game" questions |
| **Adaptive learning** | Glicko-2 ratings per concept + knowledge tracing (probability a child has mastered each concept) + spaced repetition | ▶ Continue choices, warm-ups, difficulty up and down |
| **Behaviour signals** | Heuristics first (rapid taps, idle time, error streaks, answer speed); later a small on-device classifier trained on anonymised aggregate data | Frustration, boredom, guessing and "younger sibling" detection (scenario playbook, document 11) |
| **Rule-based explanations** | Templates filled with engine facts ("Your {piece} on {square} can be captured by the {attacker}") | The first answer to every "Why?" question |
| **Speech recognition** (optional) | The device's own speech recognition, off by default, parent-enabled | Saying answers aloud ("knight!", "e4") |
| **Text-to-speech** | Platform voices for dynamic lines that have no recorded voice-over | Live explanations, names of squares |
| **Camera board recognition** (phase 3, optional) | On-device vision model reads a photo of a real board into a position | "Load my real board" so the coach can help with a game on the table |

---

## 13.4 Offline content factory (LLM in batch, reviewed by people)

This is the **most cost-efficient** use of an LLM: generate content once, have coaches review it, ship it inside the app.
Children then get instant, offline, pre-checked answers at zero running cost.

| Content | What the LLM drafts | Review step |
|---|---|---|
| **Explanation library** | For every puzzle and lesson position: 3 explanation styles (story, visual, rule-of-thumb) × 2 voices (Pip, Nova), grounded in engine facts | Automatic fact check + coach sample review |
| **Question banks** | 10+ questions per concept, with picture-friendly wrong answers (distractors) based on common misconceptions | Learning designer review |
| **Script drafts** | First drafts of lesson scripts in the document 4 format, plus simplified versions at a 5–7 year-old reading level | Learning designer edits; coach checks the chess |
| **Translation drafts** | Arabic and other languages, with chess terminology glossaries | Professional translator finalises |
| **Oops Replay phrasing** | Kid-friendly templates for each mistake type | Learning designer review |
| **Hall of Legends stories** | Short stories about historical players and games | Fact-checked by the coach |
| **Quality judge** | Checks every script and explanation for reading level, tone, length, and agreement with engine facts | Flags go to a human |

**How:** the Claude **Message Batches API** (asynchronous, about **50% cheaper** than real-time calls).
**Rough one-off cost:** 5,000 puzzles × 3 styles × 2 voices = 30,000 explanations. At about 300 input and 500 output tokens
each on Claude Opus 5.5 with the batch discount, that is in the region of **$200 in total**. This is an estimate; measure on a pilot batch first.

---

## 13.5 Live AI coach features (real time, used sparingly)

| # | Feature | Who gets it | What happens |
|---|---|---|---|
| 1 | **Coach's Corner game review** | All tracks | After a game, the engine finds up to 3 key moments; the LLM explains each in kid language and turns it into a question ("Can you find a better move here?") |
| 2 | **"Why?" button** | All tracks | Template answer first (free). If the child taps "Tell me more", the LLM explains the specific position |
| 3 | **Socratic hints** | Explorers, Academy | When a child is stuck and no pre-made hint fits, the LLM writes a guiding question instead of the answer |
| 4 | **Ask Pip / Ask Nova** | Ages 8+ with parent opt-in; Little Knights get preset question buttons only | Chess-only questions by voice or text ("Why can't my king castle?"), answered using the current position's facts |
| 5 | **Teach-back grading** | Academy | The child explains *why* a move works in their own words; the LLM compares it with the engine facts and gives feedback |
| 6 | **Parent weekly report** | Parents | Overnight batch job turns progress data into a short, friendly summary |
| 7 | **Teacher class insights** | Teachers | Overnight batch job: "5 students are stuck on castling conditions; try lesson 3.8 with them" |

Features 6 and 7 are not real-time, so they also use the batch API.

---

## 13.6 How a live AI answer is produced

```
Child taps "Why?" / finishes a game / asks Pip
            │
            ▼
┌─────────────────────────── App (device) ───────────────────────────┐
│ 1. Template answer available?  ── yes ──▶ speak it (free, instant)   │
│ 2. Pre-made library answer?    ── yes ──▶ speak it (free, offline)   │
└────────────────────────────────┬────────────────────────────────────┘
                                 │ no (only now do we go online)
                                 ▼
┌───────────────────────────── AI gateway (our server) ───────────────────────────┐
│ 3. Response cache: same position + same mistake + same track + language?  ─▶ reuse │
│ 4. Safety check of the child's question (chess-only, no personal data)            │
│ 5. Fact builder: chess.js + Stockfish → legal moves, best move, eval change,      │
│    attacked pieces, tactic tags                                                   │
│ 6. Claude call: cached system prompt (persona, safety rules, age style)           │
│    + facts JSON → structured reply                                                │
│ 7. Validator: every square, piece and move in the reply must match the facts     │
│ 8. Output safety check → text-to-speech → back to the app                         │
│    Any failure at 4, 6, 7 or 8 → friendly template answer instead                 │
└────────────────────────────────────────────────────────────────────────────────────┘
```

**The structured reply drives the app directly:**

```json
{
  "say": "Oh no! Your knight on f5 has no friends guarding it, and the pawn on g6 can take it.",
  "highlightSquares": ["f5", "g6"],
  "arrows": [["g6", "f5"]],
  "question": { "prompt": "Where could the knight go to be safe?", "answerSquares": ["d4", "e3"] }
}
```

The app speaks `say`, lights up the squares, draws the arrow, and turns the answer into one of the 12 question
types from [document 11](11-self-guided-learning.md#115-question-types). So the AI coach still *asks* rather than just tells.

### Example gateway code (TypeScript, server side only)

The API key lives only on the server. The app never calls the AI directly.

```typescript
import Anthropic from "@anthropic-ai/sdk";
import { z } from "zod";
import { zodOutputFormat } from "@anthropic-ai/sdk/helpers/zod";

const client = new Anthropic(); // reads credentials from the server environment

const CoachReply = z.object({
  say: z.string(),
  highlightSquares: z.array(z.string()),
  arrows: z.array(z.tuple([z.string(), z.string()])),
  question: z
    .object({ prompt: z.string(), answerSquares: z.array(z.string()) })
    .nullable(),
});

// Frozen text: persona, safety rules, age-style guide, output rules.
// Must never contain timestamps, names or IDs, or the cache breaks.
const COACH_SYSTEM_PROMPT = loadFrozenPrompt("coach-v1");

export async function explainMoment(facts: MomentFacts) {
  const response = await client.messages.parse({
    model: "claude-opus-5-5",
    max_tokens: 4000,
    output_config: { effort: "low", format: zodOutputFormat(CoachReply) },
    system: [
      {
        type: "text",
        text: COACH_SYSTEM_PROMPT,
        cache_control: { type: "ephemeral", ttl: "1h" },
      },
    ],
    // Only the changing part goes after the cached prefix:
    // track, language, position facts. No personal data.
    messages: [{ role: "user", content: JSON.stringify(facts) }],
  });

  // Refusal, truncation or bad output → safe template, never an error screen.
  if (response.stop_reason !== "end_turn" || !response.parsed_output) {
    return templateExplanation(facts);
  }
  const reply = response.parsed_output;
  return matchesFacts(reply, facts) ? reply : templateExplanation(facts);
}
```

Production notes:
- Log `usage.cache_read_input_tokens` to confirm the system prompt is being served from cache. If it stays at zero, something in the prefix is changing.
- Production code should also opt into Anthropic's server-side refusal fallback (`fallbacks: "default"` with the `server-side-fallback-2026-07-01` beta), alongside the template fallback above.

---

## 13.7 Making it efficient

| # | Lever | Effect |
|---|---|---|
| 1 | **Engine first, LLM last** | Most "Why?" answers are answered by templates filled with engine facts: free, instant, offline |
| 2 | **Pre-generate** the explanation library in batch | Common positions and all puzzles never need a live call |
| 3 | **Response cache** keyed by position + mistake type + track + language | Repeated situations (very common among beginners) reuse earlier answers |
| 4 | **Prompt caching** of the frozen system prompt (1-hour cache) | Cached input is billed at about a tenth of the normal price; only the small facts block is billed in full |
| 5 | **Low effort, short replies** | Explanations are 1–3 sentences; `effort: "low"` keeps thinking and output tokens small |
| 6 | **Batch API** for reports, insights and content | About 50% cheaper for anything that isn't real-time |
| 7 | **Start live coaching early** | Begin generating the game review during the end-of-game celebration, so it's ready when the child looks |
| 8 | **Per-child daily budget** for live calls | Beyond the budget, the app quietly uses templates; the child never sees a "limit" message |
| 9 | **One model, measured** | Start with one model (Claude Opus 5.5 at low effort). Only consider a cheaper model for a specific feature after the evaluation (13.9) shows it keeps quality. Claude Haiku 5.5 is about 40× cheaper per token and is the natural candidate to test for short explanations |

**Rough running cost** (an estimate to check with real measurements): one live explanation on Claude Opus 5.5 at low
effort uses a ~3,000-token cached system prompt, ~400 tokens of facts and ~400 output tokens. That is about **$0.01 per call**.
If templates, the library and the response cache answer about 90% of requests, an active child makes around 1 live call a day:
**about $0.20–$0.30 per child per month.**

**Latency targets:** first spoken word within **2 seconds**. Pip shows a "thinking" animation while waiting; templates
and library answers are instant.

---

## 13.8 Child safety and privacy rules for AI

| Rule | How |
|---|---|
| **No free chat for the youngest** | Little Knights (5–7) never send free text or voice to the LLM. They get preset question buttons only |
| **Opt-in for under-13s** | Ask Pip / Ask Nova and teach-back grading are off until a parent switches them on |
| **Chess only** | The system prompt restricts topics; an input check redirects anything else: *"Let's talk chess! What do you want to know about your game?"* |
| **No personal data** | Prompts contain only position facts, the age track and the language. No names, no device IDs; any typed text is scrubbed of names and numbers first |
| **Grounded answers** | Every reply is validated against engine facts; failures are replaced by templates |
| **Output check** | Tone and age-appropriateness check before text-to-speech |
| **Refusals handled gracefully** | A declined request (`stop_reason: "refusal"`) becomes a friendly template answer, never an error |
| **Minimal logs** | Logs are kept only for quality review with parental consent, are short-lived, and contain no identity |
| **Data retention** | Confirm the data-retention options (including zero data retention) for the chosen model with Anthropic before launch |
| **Human review** | All offline-generated content is reviewed by people before release |
| **Transparency** | The parent hub shows which AI features are on, and lets parents switch each off |

---

## 13.9 Measuring quality: the AI evaluation set

Before any AI feature ships, and before any prompt or model change:

1. **Build a test set** of about 200 real positions per feature (key moments from beginner games, puzzle positions, common "Why?" questions), each tagged with age track and language.
2. **Grade automatically** where possible: fact check against the engine (must be 100%), reading level, length, presence of a follow-up question.
3. **Grade by a coach** on a sample: correctness, kindness, clarity for the age group.
4. **Gate releases** on the scores. Compare cheaper models or lower effort only through this test set.

## 13.10 Measuring efficiency in production

| Metric | Target |
|---|---|
| Share of answers served by template / library / cache / live | ≥ 90% non-live |
| Cost per active child per month | Track against the subscription price; alert on drift |
| Prompt cache hit rate (`cache_read_input_tokens`) | ≥ 90% of system-prompt tokens |
| Latency to first spoken word | p50 < 1.5 s, p90 < 3 s |
| Fact-check failure rate | < 1% (each failure falls back to a template) |
| Off-topic or refused requests | Monitored weekly |
| Learning effect | The child solves the follow-up question after an AI explanation more often than after a template |

## 13.11 Rollout

| Phase | AI features |
|---|---|
| **P1 (MVP)** | Classic AI only on the device: Stockfish bots and hints, mistake and tactic detection, template explanations, adaptive learning. Offline content factory for Levels 1–3 |
| **P2** | Live Coach's Corner review and "Tell me more"; Socratic hints; parent weekly reports and teacher insights (batch); the evaluation set in CI |
| **P3** | Ask Pip / Ask Nova (opt-in), teach-back grading, camera board recognition, human-like bot models |
