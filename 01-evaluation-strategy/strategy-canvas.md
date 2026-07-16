# AI Evaluation Strategy Canvas

> Repo file `ai-evals/01-evaluation-strategy/strategy-canvas.md` (the repo is your submission).
> Becomes the Strategy Canvas slide of the final pitch deck you assemble in Module 6.

## 1. Product Strategy, The Context

**Target user:** VP-level Strategists and Product Leaders at Fortune 500 companies who pay a premium for verified market intelligence.

**Key use case:** Rapidly extracting specific, verified insights (e.g., comparing competitor pricing models or summarizing G2 reviews) without manual data digging.

**Value proposition:** Personalized, instant answers based on verified data, dramatically reducing the time spent finding and synthesizing information for high-stakes decisions and strategic roadmaps.

## 2. Measurements, The Execution

**User promise.** For VP-level Strategists and Product Leaders at Fortune 500 companies, Ascend IQ promises to deliver verified market intelligence data in under 10 seconds by asking plain-language questions so that they can build an informed roadmap without any manual digging.

**Top 3 trust metrics:**
- **Latency**, Response speed (P95 / P99). Slow kills engagement.
- **Hallucination Rate**, % of outputs that are confidently false or fabricated.
- **Fairness**, Quality consistency across user groups, geos, languages.

**Why these three:** • Latency: <10s response is key to make sure we replace manual digging. If it's too slow, they will go back to manual digging.
• Hallucination rate: Our persona pays $50k+ annually for verified data to inform their roadmaps.;  this means that showing them incorrect or unverified data might put the contract at risk.
• Fairness: We want to make sure that the market data is delivered as is, and doesn't change based on who's asking or who the data is about.

## 3. Strategic Trade-Offs, The Cost

### Trade-off 1 · Hallucination Rate ↔ Latency
We prioritize Hallucination Rate over Latency because verified but slower data is better than not 100% correct but fast.

### Trade-off 2 · Fairness ↔ Latency
We prioritize Fairness over Latency because we prioritize having lower legal risk over giving immediate answers.

---
_Generated from the AI Evaluation Strategy Canvas, M1 lab tool, AI Evals Certification._


# Evaluation Strategy Canvas

> Module 1 · Evaluation Strategy, ★ Deliverable 1
>
> The one-page bet that frames everything else: what you're evaluating, why it matters, and what "good enough to ship" means.
> This is a living document, fill in what you can now and refine it as the course progresses.

## 1. The feature under evaluation

_What LLM-powered feature are you evaluating? Describe the input, the output, and the user._

- **Input:** _What does the user (or system) provide?_
- **Output:** _What does the feature produce?_
- **User & job-to-be-done:** _Who relies on it, and for what?_

## 2. Why evals: the cost of being wrong

_What happens when this feature fails silently? (e.g. wrong answer ships, trust erodes, compliance risk.)_

## 3. Quality dimensions

_Which dimensions actually matter here, and how do you weight them?_

| Dimension | Why it matters | How you'd measure it |
|---|---|---|
| _Correctness / faithfulness_ | _…_ | _…_ |
| _Safety / policy_ | _…_ | _…_ |
| _Tone / format_ | _…_ | _…_ |

## 4. Evaluator strategy

_For each dimension: human review, code/heuristic check, or LLM-as-judge? Why?_

| Dimension | Evaluator type | Rationale |
|---|---|---|
| _…_ | _human / code / LLM-judge_ | _…_ |

## 5. "Good enough to ship": the bar

_What threshold per dimension makes this shippable? What's the non-negotiable floor?_

## 6. Risks & unknowns

_What might this canvas be wrong about? What will you learn in Module 2's failure discovery?_

## Link to full artifact

_[link / screenshot]_
