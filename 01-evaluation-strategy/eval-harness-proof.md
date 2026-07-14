# First LLM-as-a-Judge Eval — Module 1

> Module 1 · First Eval Lab · ★ Deliverable 2
>
> How you wired your first eval harness — an LLM-as-a-Judge running over a dataset — and beat the cold start by seeding a starter dataset. Capture the **setup and your definition of "good"** here; the full scored run against a curated golden set comes later.

## Version A — Concise (system prompt used)

```text
You are an executive briefing assistant.
Summarize in exactly 3 bullet points under 60 words. No preamble, no extra text.
```

## Version B — Narrative (system prompt used)

```text
You are a PR communications assistant.
Write a 100-word narrative summary highlighting wins first, then risks and next steps. Keep a positive tone. No bullets.
```

## Eval setup — dataset name + judge model/family

_What dataset are you evaluating, which evaluator/metric, and which model judges it?_

> Example: dataset `Module1Output`, evaluator `Conciseness (LLM-as-a-Judge)`. Generator = a small model from Provider X; **judge = a small model from a different family (Provider Y)** to avoid self-preference bias.

## Cold-start — the prompt you used to seed a starter dataset

_You don't have production data yet. Paste the prompt you gave a chatbot to generate ~20 example rows so you can start evaluating today._

> Example: "Generate 20 example rows for evaluating email-summary quality. Each row: input email + candidate summary + a first-pass label (good/bad) + one-line reason. Make ~half concise/faithful (good) and half verbose or inaccurate (bad). Return as a markdown table."

## Your definition of good vs bad (golden-set criteria)

_This rubric is the whole point — the judge only scores against what you decide "good" means._

> Example: **Good** = faithful to the email, no invented facts, ≤60 words, decision-ready for a CEO. **Bad** = adds claims not in the source, buries the key number, or rambles past 100 words.

## Screenshots — links or repo paths

_Drop image links, or commit images under `01-evaluation-strategy/screenshots/` and reference them._

| What it shows | Screenshot / link |
|---|---|
| Eval setup (dataset + judge) | _…_ |
| Starter dataset rows | _…_ |

---

_Self-review: Is your judge from a **different model family** than the generator? Does your "good vs bad" rubric describe the product outcome, not just formatting? Could a teammate re-run this from your notes alone?_
