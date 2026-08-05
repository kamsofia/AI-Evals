# Module 4 · Launch Strategy · Section 4.0 Release Criteria

_Generated from the M4 Launch Strategy Builder. Drop this into your PRD as Section 4.0._

## 4.0 Release Criteria

The following thresholds must be met by Model Candidate v1.x before approval for production deploy. Eval Specs from Module 3 define the measurement methodology.

| Severity | Metric | Threshold | Dataset | Method |
|---|---|---|---|---|
| 🔴 Hard (Blocker) | Pricing Hallucination Rate | = 0% | `Ascend_IQ_Logs` | https://github.com/kamsofia/AI-Evals/blob/main/03-eval-suites/lab-1-eval-suite.md |
| 🟡 Soft (Review) | Tone Consistency | ≥ 4.0 / 5 | `Ascend_IQ_Logs` | _[Example Spec]_ |
| 🔵 Advisory (Monitor) | Latency | < 2.0s | `Ascend_IQ_Logs` | _[Example Spec]_ |

## 4.1 CI Gate Policy

These thresholds run in a GitHub Actions gate on every pull request, replaying deterministic fixtures from the regression golden set (≥ 30 cases). PM owns the policy; Engineering owns the YAML.

> Block the merge on any Hard Gate regression — a single pricing hallucination in the golden set (0%, zero tolerance) fails the build. A 1-point drop in the Tone Consistency score (below 4.0/5) warns but doesn't block; flagged for review at Staging. Latency exceeding the 2.0s  budget warns only, logged for trend tracking, never blocks the merge.

## 4.2 Mitigation Plan · Soft Gate

**Selected Lever:** Feature Flagging

> If our Soft Gate fails (Tone Consistency score falls below 4.0/5 on customer-facing drafts (cold emails, outreach copy) in more than 10% of a given week's flagged outputs.), we recommend **Feature Flagging** because Auto-disables the cold-email drafting feature if the production tone score crosses threshold, stopping bad output from reaching a customer at all — a real engineering control Engeneering can wire up, not just a disclosure.

---

_Lab artifact for Module 4, AI Evals Certification, Product School. Becomes the Eval Gates slide of the Final Project deck._
