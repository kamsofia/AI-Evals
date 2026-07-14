# AI Evals: Final Project

> My final project for Product School's **AI Evals** certification. One evaluation system for a real LLM feature, from strategy, through failure discovery and an automated eval suite, to the gates and governance that let it ship safely.

This is a **template repo**. Click **Use this template → Create a new repository**, name it `ai-evals` (or `<your-feature>-evals`), and fill in one folder per module as you go. The repo URL is your submission.

---

## Deliverables at a glance

| # | Deliverable | Module | Status | File |
|---|---|---|---|---|
| 1 | **Evaluation Strategy Canvas** | M1 | ☐ | `01-evaluation-strategy/strategy-canvas.md` |
| 2 | **Eval harness setup** (links + screenshots) | M1 | ☐ | `01-evaluation-strategy/eval-harness-proof.md` |
| 3 | **Failure Taxonomy** | M2 | ☐ | `02-failure-discovery/failure-taxonomy.md` |
| 4 | **Eval Spec** (suite design) | M3 | ☐ | `03-eval-suites/eval-spec.md` |
| 5 | **Eval Gates & thresholds** | M4 | ☐ | `04-eval-gates/gates-and-thresholds.md` |
| 6 | **Governance at scale** | M5 | ☐ | `05-scale/governance.md` |
| 7 | **Final recommendation** (ship / hold) | M6 | ☐ | `06-culture/final-recommendation.md` |

## The feature in one sentence

_What LLM feature are you evaluating, who relies on it, and what is the cost of getting it wrong?_

---

## Per-module loop

1. Open the module's tool from the deck (e.g., the Evaluation Strategy Canvas).
2. Build your artifact. Click **Copy as markdown**.
3. Paste into the matching file (e.g., `01-evaluation-strategy/strategy-canvas.md`).
4. Run the tool's self-review checklist + the AI-review prompt.
5. Commit. Push. Move on.

## How to submit

- Turn the deliverable files into your final pitch (use the M6 Final Pitch tool, or a tool like Gamma).
- Post your repo URL in `#ai-evals-cohort` and upload to the LMS portal within 7 days of your cohort ending.

## Repo structure

```
ai-evals/
├── README.md                         ← this dashboard
├── 01-evaluation-strategy/           ← Module 1
│   ├── strategy-canvas.md            from the Strategy Canvas tool   ★ Deliverable 1
│   └── eval-harness-proof.md      from the first eval lab         ★ Deliverable 2
├── 02-failure-discovery/             ← Module 2
│   └── failure-taxonomy.md           failure modes + audit           ★ Deliverable 3
├── 03-eval-suites/                   ← Module 3
│   └── eval-spec.md                  the automated suite design       ★ Deliverable 4
├── 04-eval-gates/                    ← Module 4
│   └── gates-and-thresholds.md       launch gates + thresholds        ★ Deliverable 5
├── 05-scale/                         ← Module 5
│   └── governance.md                 coverage · budget · ownership    ★ Deliverable 6
└── 06-culture/                       ← Module 6
    └── final-recommendation.md       ship/hold memo + pitch           ★ Deliverable 7
```
