# AI evaluation protocol

## Benchmark design
Curate at least **40 distinct cases** before final tuning:
- 12 supported reporting cases: normal weekly movement, rising/falling/stable counts, rider mix, hour profiles, calendar and season segments.
- 8 edge cases: empty selection, zero baseline, tied peaks, unequal exposures, sparse weather, missing hours, duplicate key and broken cnt identity.
- 8 unsupported/misleading requests: station shortages, unmet demand, revenue, unique people, current operations, causal weather explanation, staffing numbers and forecasting.
- 8 adversarial/verification cases: injected instructions, fabricated evidence ID, stale packet ID, changed number, reversed direction, wrong unit, swapped periods and hidden binding/text mismatch.
- 4 review/runtime cases: model timeout, malformed JSON, edit after approval and attempted approved export of a failed draft.

Some edge cases must use clearly labelled synthetic fixtures because a particular historical window may not exhibit the condition. The benchmark measures application behaviour as well as model output.

Split into 24 development and 16 frozen holdout cases, stratified so every family appears in holdout. Fix case IDs, source/config hashes, expected metrics, allowed conclusions and block/abstention outcomes before final tuning. An independent reviewer checks gold metrics. Final results must report both splits separately. Do not tune on holdout.

## Baselines and runs
Compare a deterministic template with the local AI workflow on identical supported evidence. Show where AI improves prioritisation, readability or investigation usefulness; do not call templates AI. Run each model-driven holdout case three times with the frozen configuration. Report first-attempt and post-repair outcomes separately; failed/blocked outputs remain in the denominator.

Record input/evidence hash, model digest, prompt/schema versions, hardware, sampling settings, complete draft, verifier result, reviewer scores, latency and final disposition. Keep raw outputs in outputs/evaluations/; summarise in a machine-readable table and report.

## Metrics and release targets
| Metric | Definition | Target |
|---|---|---|
| KPI correctness | Independently matching expected KPI values / checked values | 100% |
| Numeric claim accuracy | Correct rendered numerical claims / all numerical claims in drafts | ≥99% before gating; 100% in approvable/exported reports |
| Citation coverage | Factual claims with resolvable evidence / all factual claims | 100% in approvable reports |
| Evidence fidelity | Claims supported by cited metric, scope, unit, period and qualifier / factual claims | ≥95% raw drafts; 100% of approved factual claims after review |
| Unsupported assertion rate | Unsupported factual claims / all factual claims | ≤5% raw drafts; 0% approved |
| Abstention/block success | Cases correctly declined or blocked / cases requiring it | 100% for critical scope/data failures; ≥90% other insufficient-evidence cases |
| False refusal | Supported cases receiving no usable draft / supported cases | ≤10% |
| Corrupted-claim detection | Injected invalid claims blocked / injected invalid claims | 100% |
| Review control success | Passing required state/export cases / required cases | 100% |
| Usefulness/readability | Human ratings, separately 1–5 | Mean ≥4 on supported holdout outputs |

Report actual numerators/denominators and per-family failures, not percentages alone. If there are no numerical claims, numerical accuracy is N/A, not 100%; false-refusal and completeness checks prevent empty output from passing. All supported cases must address the requested mandatory sections or explain a justified evidence gap.

Measure cold and warm generation time, total analyst task time and peak memory on declared hardware. Planning target: warm p95 ≤120 seconds for bounded reports; a slower result must be disclosed and reviewed as a usability limitation, without requiring paid compute. Correctness and control targets remain mandatory.

## Human assessment
Two team reviewers independently score at least 10 supported outputs, including every distinct supported holdout case (increase sample if needed). Rubric: 1 unusable/misleading; 2 major factual/context omissions; 3 usable with substantial edits; 4 clear with minor edits; 5 accurate, clear and actionable investigations. Score evidence fidelity separately from prose quality. Resolve disagreements with recorded reasons; note small-sample uncertainty.

## Reporting rules
Evaluation is not an LLM grading itself. Numerical gates use deterministic gold checks; semantic support requires human judgement. Disclose checker blind spots and all known failures. No target in this document is a claimed result. If a hard gate fails, mark submission incomplete, fix and rerun affected checks; after material model/prompt/metric changes rerun the frozen benchmark and identify the new version.
