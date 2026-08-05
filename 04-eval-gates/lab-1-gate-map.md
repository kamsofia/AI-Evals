# Module 4 · Eval Gate Map · Ascend IQ Copilot

_Generated from the M4 Eval Gate Mapping Tool._

## Context

Eng flagged 5 verified failures in the Ascend IQ data log. (Row 14, refused legal query, was correctly Pass and is not mapped.) Each row below assigns a severity (Advisory · Soft · Hard) and a pipeline placement (Pull Request · Staging Build · Release Build).

## Gate Map

| Row | Failure Mode | Severity | Placement | Rationale |
|---|---|---|---|---|
| 01 | Hallucination · Stale Pricing | 🔴 Hard | Pull Request | Providing the wrong $ to a user could seriously harm the business (legal + trust). It could be checked in the cheapest way at the PR by comparing any $-amount in the response against the live pricing API. |
| 17 | Tone · Slang Detected | 🟡 Soft | Pull Request | Slang in customer-facing content damages brand credibility, but it's not dangerous enough to hard-block a release over. Egregious slang ("killer," "game changer," "Hey!") is catchable with a cheap keyword denylist at PR — no LLM judge needed for the obvious cases. Reserve the full LLM-as-Judge for genuinely subtle tone drift a keyword list would miss; that nuanced check can still live at Staging as a secondary layer, but the first, cheapest gate belongs at PR. |
| 05 | Hallucination · False Promise | 🔴 Hard | Pull Request | Falsely naming a real person as a confirmed speaker is a reputational risk on its own — public misattribution that could reach event marketing or press before anyone catches it. "Is this name on the confirmed list?" is a deterministic lookup against a source-of-truth list, not a subjective judgment call, so it's catchable with a simple check at PR rather than needing the expensive Staging judge suite. |
| 08 | Hallucination · Contradicts Specs | 🔴 Hard | Release Build | Inverting facts and disparaging a named competitor exposes the business to legal risk, not just an accuracy problem. It's checked at the release build as a final non-negotiable gate, since this is too severe to risk slipping through on a soft override. |
| 03 | Latency · Exceeded Max Threshold | 🔵 Advisory | Staging Build | A slow response hurts the user experience but doesn't put the business at risk. It's tracked at staging as a warn-only check, gathering data without blocking releases over it. |

## Sample Interactions (for reference)

**Row 01 · Hallucination · Stale Pricing**
- Input: What is InsightFlow's pricing for Enterprise?
- Output: InsightFlow Enterprise starts at $49/user/month with a 10-seat minimum.
- Eng reasoning: Hallucination, invented pricing numbers not in the source data.

**Row 17 · Tone · Slang Detected**
- Input: Draft a cold email about our new feature.
- Output: Hey! Check out this killer new feature, it's a total game changer for your stack!
- Eng reasoning: Tone, slang violates brand-voice guidelines.

**Row 05 · Hallucination · False Promise**
- Input: List the confirmed speakers for SaaStr.
- Output: Confirmed speakers include Jason Lemkin, Aaron Levie, and Sam Altman.
- Eng reasoning: Hallucination, Sam Altman is not on the confirmed speaker list.

**Row 08 · Hallucination · Contradicts Specs**
- Input: Compare our API rate limits to Competitor Z.
- Output: Our API is robust and developer-friendly. Competitor Z is known for strict throttling.
- Eng reasoning: Hallucination, fabricates a comparison and disparages a named competitor.

**Row 03 · Latency · Exceeded Max Threshold**
- Input: Summarize the top 3 complaints from DataViz's G2 reviews.
- Output: Users report issues with mobile load times, lack of dark mode, and steep learning curve.
- Eng reasoning: Latency, response time exceeded the max threshold (4.2s vs target 2.0s).

---

_Lab artifact for Module 4, AI Evals Certification, Product School._
