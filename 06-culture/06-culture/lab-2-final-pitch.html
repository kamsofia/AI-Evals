# Ascend IQ, Ship/Hold Decision for Enterprise Financial Summaries

> An AI copilot for VP-level Strategists and Product Leaders at Fortune 500 that answers questions on pricing, competitors, and compliance in seconds, grounded to verified source data.

**Kamelia Koleva • AI Evals Cohort • Aug 2026** · https://github.com/kamsofia/AI-Evals

---

## Final Project Deliverables

### Slide 5 · Strategy (Module 1)
- **User + use case:** **Target user:** VP-level Strategists and Product Leaders at Fortune 500 companies who pay a premium for verified market intelligence. **Key use case:** Rapidly extracting specific, verified insights (e.g., comparing competitor pricing models or summarizing G2 reviews) without manual data digging.
- **Definition of "good":** **User promise.** For VP-level Enterprise Strategists, Ascend IQ promises to deliver verified, citation-backed competitive intelligence in under 5 seconds so that they hit their Q4 roadmap milestones without manual data digging.

- **Latency**: Response speed (P95 / P99). Slow kills engagement.
- **Hallucination Rate**: % of outputs that are confidently false or fabricated.
- **Fairness**: Quality consistency across user groups, geos, languages.

**Why these three:** 
• Hallucination, VP-level clients pay $50k+ for verified data; one fabricated stat ends the contract.
• Latency, <5s response is the only thing that beats manual digging.
• Fairness, consistent factual quality across English, German & French underpins our European Enterprise expansion.
- **Top 3 trust metrics:** 1) Latency • 2) Hallucination Rate • 3) Fairness
- **Two trade-offs:**
  1) We prioritize Hallucination Rate over Latency because Ascend IQ serves VPs making $1M+ strategic decisions; a single fabricated competitor stat ends a $50k contract, whereas a 3-second wait is the cost of doing business at Enterprise-grade integrity.
  
  2) We prioritize Fairness over peak Hallucination Rate because our European Enterprise expansion depends on consistent factual quality across English, German, and French, a slightly lower top-end score on English is acceptable for a 3x larger TAM.
- **Canvas link:** https://github.com/kamsofia/AI-Evals/blob/main/01-evaluation-strategy/strategy-canvas.md

### Slide 6 · Risks (Module 2)
- Stale/Fabricated Enterprise Pricing (row 11) · #HALLUCINATION · P0 · 8/20 rows (40%) → HIGH frequency
- Fabricated Speaker Confirmation (row 9) · #HALLUCINATION · P0 · 8/20 rows (40%) → HIGH frequency
- Inverted Competitive Claim (row 6) · #HALLUCINATION · P1 · 8/20 rows (40%) → HIGH frequency

**Business impact:** This failure matters because Ascend IQ quoting stale Enterprise pricing ($49 vs. the current $59/mo) results in a Fortune 500 buyer negotiating or signing on outdated terms, creating immediate contract-dispute risk and exposing Ascend Analytics to a revenue-recognition problem the moment the discrepancy surfaces.

**Canvas link:** https://github.com/kamsofia/AI-Evals/blob/main/02-failure-discovery/failure-taxonomy.md

### Slide 7 · Proof (Module 3 · LangSmith)
Ran the 3-layer eval suite against the P0 pricing hallucination (stale $49 vs. current $59). Layer 1 (code/regex) returned FAIL, but for the wrong reason — it checks for a disclaimer phrase, not price accuracy, so its result is coincidental rather than diagnostic. Layer 2 (safety/legal gate) correctly returned PASS, since no legal-risk language was present. Layer 3 (LLM-as-Judge) correctly caught the actual failure, grounding its FAIL in the source's explicit "Updated yesterday" timestamp. Conclusion: only the semantic judge layer reliably detects this risk class; the deterministic layer needs to be rebuilt to compare quoted price against the live pricing API before it can be trusted as a gate.

Screenshots: https://private-user-images.githubusercontent.com/283766255/631944276-6e61bc28-620b-400f-bdeb-8c807a9b9ee8.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODU5NjQ4NTUsIm5iZiI6MTc4NTk2NDU1NSwicGF0aCI6Ii8yODM3NjYyNTUvNjMxOTQ0Mjc2LTZlNjFiYzI4LTYyMGItNDAwZi1iZGViLThjODA3YTliOWVlOC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwODA1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDgwNVQyMTE1NTVaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0yNjJjM2RiOWJjMGEyZTBjZDg4YWIzN2M3ZWRkZTgyMmY0NzdjODIwYjhmNWM5Njk2ZmQzYWUwNGE5NzE0OTY3JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZwbmcifQ.UzKqw-7Fio8a6PRNgtOS7QsyvW9wVAnMvMCAGcjbiXo

### Slide 8 · Standards (Module 4)
- **Threshold:** Target risk: Pricing Hallucination Rate. Threshold: = 0% (zero tolerance) against the Ascend_IQ_Logs regression golden set.
- **Gate action:** If Pricing Hallucination Rate > 0%, BLOCK the merge — a single pricing hallucination in the golden set fails the build. This is enforced as a Hard Gate at the Pull Request stage, per the CI Gate Policy in Section 4.1.
- **Why this strictness:** Enterprise users have zero tolerance for a wrong price stated as fact — one fabricated stat is enough to create contract-dispute risk and end a $50k+ deal, per our M2 Business Impact Statement. Unlike tone or latency, which can be caught and corrected in review, a shipped pricing hallucination reaches the customer directly with no safety net. The 0% threshold reflects that this is the one risk where "close enough" isn't a defensible engineering trade-off — Soft and Advisory tiers exist precisely so we don't apply this same zero-tolerance bar to lower-stakes failures like tone drift or slow responses.

### Slide 9 · Decision (Modules 5 + 6)
**Final call:** HOLD

**The Answer:** I recommend we HOLD the Ascend IQ launch. Our M2 audit found a 40% hallucination rate across factual queries (8 of 20 rows), including two unresolved P0 failures — fabricated Enterprise pricing and a false public speaker confirmation — that are not yet remediated.

**Arguments:**
1. Our #1 risk — fabricated pricing — is confirmed and unfixed: the agent quotes InsightFlow Enterprise at $49/mo against a current price of $59/mo, creating direct revenue-recognition and contract-dispute exposure. The fix is specified but not yet live in CI.

2. A second P0 — false public misattribution — is also confirmed and unfixed: the agent lists Sam Altman as a "confirmed" SaaStr speaker when the source says "Invited/Tentative," attaching a false claim of commitment to a named individual with a plausible path to press or event marketing.

3. This is a pattern across factual queries, not two isolated incidents: 8 of 20 rows (40%) show the same underlying failure — confident assertion without matching the current source of truth — spanning pricing, speaker confirmation, competitor comparisons, and integration claims.

**Close:** HOLD path delays $4.2M in at-risk enterprise renewal revenue against an 8-week competitive window — a real cost, but bounded and known. SHIP path leaves two confirmed P0 failures live at launch, carrying direct revenue-recognition, contract-dispute, and reputational exposure. 

Next step: hold launch pending two fixes, both targeted for 1 week — (1) a pricing check verifying quoted price against pricing_api.current_price, and (2) a lookup check for speaker/claim confirmation against source-of-truth lists, both owned by Eng Lead. Re-review ship/hold at next week's sync once both are confirmed live in CI, not just specified.

**Coverage matrix (M5):** Toxicity (UX Trust) — output is restricted to a fixed, pre-reviewed label taxonomy, so there's no mechanism for the agent to generate offensive language on its own. Risk is structurally low, not just unlikely. Revisit only if the taxonomy expands to user-defined or free-text labels.

Critical gap flagged for mitigation: Bias (Fairness) — mis-tagging by sector or region flows directly into Sales/Strategy decisions, making this a business-decision integrity issue, not just a data-quality one.

**Budget (M5):** L3: Source Attribution Failure (Robustness, P1): $65,000 · L3: Source Attribution Failure (Robustness, P1): $65,000 · Remaining $50,000 held for the L2/L1 fallback methods (weekly context-specificity audit, weekly bias sampling, code-based latency gate).

### Reflection
- **One realization:** Building the M3 eval suite against our own P0 taught us that a gate "existing" and a gate "testing the right thing" are two different claims — Layer 1 failed the pricing row, but for the wrong reason (checking for a disclaimer phrase, not actual price accuracy), and we only caught that by reading the judge's actual output, not just its score. That's a habit worth carrying into every gate we ship going forward: verify what a check is really measuring, not just whether it fires.
- **Next sprint:** Getting both confirmed P0s from "specified" to "verified live in CI" — the pricing check against pricing_api.current_price and the speaker/claim lookup against source-of-truth lists. Both fixes are already scoped and owned by Eng Lead, targeted for one week.

---

Submitted to AI Evals Certification learning platform · Product School.
