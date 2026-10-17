# MTL-AI-047 — Submission guide

## Release sequence

1. Finish D1–D12 and link agreed user requirements to deliverables, acceptance criteria, tests and evidence.
2. Confirm the UCI source manifest, licence/attribution, hourly/daily grain controls and reviewer restore access.
3. Freeze KPI formulas, comparison-window/coverage rules, evidence schema, prompts, local model/runtime and dependency lock.
4. Run the deterministic KPI engine before every narrative evaluation. Preserve evidence packets, raw model outputs, verification results, blocked claims and failures.
5. Execute project domain/claim-verification tests and **three UAT tasks**. Resolve all critical/high defects and retain retests.
6. A distinct member performs a clean rerun and reconciles deterministic KPIs/evidence IDs.
7. Produce a 2-page management brief, 8–12 slides and a 5–10 minute demo for the **Mobility Operations Manager**.
8. Complete `submission/FINAL_SUBMISSION.md`, contribution evidence and evidence index.
9. Tag the evaluated commit **`v1.0-mettelo-submission`** and verify reviewer access.

## Walkthrough

Demonstrate one valid comparison, one coverage-blocked comparison, one verified narrative, one deliberately corrupted claim rejected by the verifier and one human-approved export.

Explain that the AI does not calculate metrics and that historical rental records cannot establish capacity shortage, unmet demand, revenue or causal weather effects.

## Required evidence bundle

Team repo/final SHA/tag; reviewed master commit; source manifest; traceability; KPI catalogue; evidence packets; baseline/local-model outputs; held-out evaluation with denominators; blocked/rejected claims; UAT/defects; independent rerun; handover; decision brief/demo; contributions.

Reviewer records **ACCEPTED / REWORK / BLOCKED** with actual reviewer/date, simulated sponsor role and unresolved issues/owners.
