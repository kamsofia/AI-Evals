# Ship/Hold Memo · Ascend IQ

> **Decision:** 🛑 HOLD

**To:** CPO · cc Eng Lead · Trust & Safety  
**From:** Kamelia Koleva · AI Evals Cohort · 5 Aug 2026

## The Answer

I recommend we HOLD the Ascend IQ launch. Our M2 audit found a 40% hallucination rate across factual queries (8 of 20 rows), including two unresolved P0 failures — fabricated Enterprise pricing and a false public speaker confirmation — that are not yet remediated.

## The Arguments

### 1. Our #1 risk — fabricated pricing — is confirmed and unfixed.

Our latest audit shows the agent quoting InsightFlow Enterprise pricing at $49/mo when the current price, updated the day prior, is $59/mo. This is our highest-severity finding: a wrong price stated as fact in a B2B sales context creates direct revenue-recognition and contract-dispute exposure. The fix is specified (compare quoted price against pricing_api.current_price, zero tolerance) but not yet live. We should not ship until this specific check is verified working in CI, not just documented.

### 2. A second P0 — false public misattribution — is also confirmed and unfixed.

The latest audit also shows the agent listing Sam Altman as a "confirmed" SaaStr speaker when the source lists him as "Invited/Tentative." This attaches a false claim of commitment to a named, real individual, with a plausible path to reaching event marketing or press before review. This failure needs a dedicated fix — a lookup check against the confirmed-speaker source of truth — before we can consider it closed.

### 3. This is a pattern across factual queries, not two isolated incidents.

Across the 20-row audit, 8 rows (40%) show the same underlying failure: the agent asserts a fact confidently without it matching the current source of truth — spanning pricing, speaker confirmation, competitor comparisons, and integration claims. Fixing the two P0s closes our most severe exposure, but the recurrence rate tells us this is worth treating as one factual-grounding problem, not three unrelated bugs to patch individually.

## Evidence · Trust Metrics

```
- Hallucination frequency: 8/20 rows (40%) — Gate: ≥3 = high frequency — CONFIRMED HIGH · Source: M2 audit
- Pricing accuracy (row 11): $49 quoted vs. $59 actual — Gate: 0% tolerance — FAIL, unresolved · Source: M2 audit + M3 eval suite run
- Judge-layer detection (row 11): Layer 3 (semantic) correctly flagged; Layer 1 (code) failed for the wrong reason (disclaimer-phrase check, not price check) — coverage gap identified, fix pending · Source: M3 3-layer run
- Speaker confirmation (row 9): Sam Altman listed "confirmed" vs. actual "Invited/Tentative" — FAIL, unresolved · Source: M2 audit
- Competitor claim (row 6): rate limit comparison factually inverted — Gate: Hard/Release — FAIL, gate assigned, not yet verified live · Source: M2 audit + M4 gate map
- Tone (row 17): slang in cold-email draft — Gate: Soft/PR keyword check — FAIL, mitigation specified, not yet shipped · Source: M4 gate map
- Latency (row 3): 4.2s vs. 2.0s target — Gate: Advisory — flagged, non-blocking · Source: M4 gate map
```

## Business Risk

HOLD path: delays $4.2M in at-risk enterprise renewal revenue against an 8-week competitive window. A real cost, but bounded and known.

SHIP path: two confirmed P0 failures (pricing, speaker confirmation) remain unresolved at launch. A misquoted enterprise price or a public misattribution reaching a real customer or outlet carries direct revenue-recognition, contract-dispute, and reputational exposure — the exact scenarios our audit surfaced.

## Next Step · Decision Needed

Hold launch pending two fixes, both targeted for 1 week: (1) ship a pricing check that verifies quoted price against pricing_api.current_price — Eng Lead owns; (2) ship a lookup check for speaker/claim confirmation against source-of-truth lists — Eng Lead owns. Re-review ship/hold at next week's sync once both are confirmed live in CI, not just specified.

## Reflection

_Building the M3 eval suite against our own P0 taught us that a gate "existing" and a gate "testing the right thing" are two different claims — Layer 1 failed the pricing row, but for the wrong reason, and we only caught that by reading the judge's actual output, not just its score. That's a habit worth carrying into every gate we ship going forward: verify what a check is really measuring, not just whether it fires._
