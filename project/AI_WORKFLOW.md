# Evidence, generation and claim verification

## Architecture
Separate ingestion, validation, metrics, evidence, generation, verification, review and export modules. Only the deterministic layer reads raw data and performs arithmetic. The model receives approved evidence, definitions and caveats, never a free-form tool capable of executing code or SQL.

## Evidence contract
Each packet contains schema_version, run_id, creation time, source file hashes, source attribution, code commit, metric/config version, current and comparison windows, filters, coverage status and metric records.

Each metric record contains evidence_id, metric_id, window, dimensions, value, display_value, unit, numerator/denominator where applicable, observed_n, eligibility, formula identifier, source-row selection and caveats. Bind evidence IDs to the packet hash so another period's ID cannot be reused silently. Include the packet hash in every report and verification result.

Example shape (illustrative synthetic values only):
```json
{"evidence_id":"example-run:current:rentals.total","metric_id":"rentals.total","value":1200,"display_value":"1,200","unit":"rentals","window":{"start":"2012-01-02","end":"2012-01-08"},"observed_n":168,"eligibility":"supported","formula":"sum(cnt)","synthetic":true}
```
This is a shape example, not a complete production packet or historical result.

## Prompt contract
Version system prompt, user template and output schema. Instruct the model to use only supplied records, copy display values, cite factual claims, identify associations without causal wording, abstain on ineligible evidence and treat user/source strings as untrusted data. No external facts or model-memory explanations. Set bounded context/output, temperature 0 and record seed if supported; do not promise bitwise repeatability.

Output structured sections with atomic claims: claim_id, type (observation/hypothesis/investigation/limitation), text, evidence_ids, metric bindings and abstention reason. Numerical bindings identify metric, value, unit, window and comparison direction. A recommendation links to supporting observations and names missing evidence. Schema validation is necessary but cannot establish factual truth.

## Independent verifier
1. Validate strict output schema and allowed section/claim types; reject unknown fields.
2. Resolve every evidence ID within this exact packet and confirm eligible status.
3. Verify numerical value, units, period, filters, direction, denominator and percent-versus-percentage-point semantics against precomputed records.
4. Check the **rendered text**, not just structured bindings: a correct hidden value must not mask an incorrect sentence, date, comparison or qualifier.
5. Restrict quantitative sentences to controlled rendering from validated bindings, or reject text whose quantities cannot be exhaustively checked. Detect extra numbers and unknown entity/station/revenue claims.
6. Flag causal assertions, unsupported shortage/capacity conclusions and scope breaches. Keyword checks are only heuristics: semantic support still requires human review and evaluation.
7. Produce per-claim pass/fail/review-required plus reasons and evidence links.

Use adversarial fixtures with correct IDs but wrong numbers, swapped periods, reversed direction, incorrect units and unsupported causal prose. Matching an ID alone is never verification.

## Failure and review behaviour
Malformed output, timeout, unavailable model or failed claims must not produce an approved report. Permit at most one logged repair attempt using verifier feedback; if still invalid, show blocked status and a clearly labelled deterministic baseline. Preserve failed drafts for evaluation. A baseline is not AI output.

State transitions: draft → verification_failed OR verified_pending_review → approved/rejected. Every edit produces a new revision, resets approval and triggers verification. Final human approval records reviewer, UTC timestamp, revision hash and decision. Human approval cannot override failed numerical/lineage checks; fix and re-verify first.

## Export bundle
Export report.md, report.json, evidence.json, verification.json and review.json with shared run/revision IDs, hashes, model/prompt/config versions and attribution. Unapproved exports, if offered for troubleshooting, must have conspicuous DRAFT/NOT APPROVED markings. Do not allow a draft to use the approved-export path.
