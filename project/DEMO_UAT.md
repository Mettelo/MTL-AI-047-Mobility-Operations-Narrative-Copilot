# Final demo and UAT

Run a short live walkthrough on the submitted version, supported by saved outputs. A video is useful but not a substitute for local reproduction.

| Case | Action | Expected outcome |
|---|---|---|
| UAT01 | Select valid historical current/comparison weeks | Visible windows, coverage, source hashes and exact deterministic KPIs |
| UAT02 | Generate fresh local AI draft | Required narrative sections, local model identity and evidence links |
| UAT03 | Open a movement/weather claim | Matching metric, unit, filter, denominator, sample size and caveat |
| UAT04 | Inject changed number with valid ID | Verification fails and approved export is blocked |
| UAT05 | Ask for station shortages/revenue/weather cause | Explicit insufficient-evidence response; no invented conclusion |
| UAT06 | Load missing-hour/sparse group fixture | Coverage/eligibility warning and required suppression/abstention |
| UAT07 | Approve, then edit report | New revision resets approval; re-verification and new sign-off required |
| UAT08 | Export approved revision | Markdown/JSON/evidence/verification/review hashes agree |
| UAT09 | Stop model or return malformed JSON | Visible recoverable failure, no false success or approval |
| UAT10 | Reproduce after downloads without internet | Core flow, tests and evidence available at £0 |

Record expected and actual results, case ID, date, tester, code/config/source/model versions, artifact links and defects in submission/UAT_RESULTS.md. Include an analyst reviewer who assesses clarity and scope. Fix failed hard gates and retest; keep original failure evidence. Final sign-off identifies the exact commit/tag reviewed.
