# Acceptance criteria

All hard gates require evidence links in the final submission. An attractive UI or fluent draft cannot compensate for a failed gate.

| ID | Gate | Required proof |
|---|---|---|
| AC01 | Reproducible approved data | Real source manifest, hashes, licence/attribution, row/date/grain audit and exact acquisition instructions |
| AC02 | Validation blocks bad data | Automated tests for duplicate keys, invalid values and count identity; visible failure; no narrative generated |
| AC03 | Deterministic KPIs | Every catalogue metric implemented; independent full-window + three-group reconciliation; 100% expected fixture values |
| AC04 | Correct coverage/comparison policy | Missing-hour report, 95% coverage gate, valid equal-duration windows, zero-baseline and sparse-group handling |
| AC05 | Evidence lineage | Report claims resolve to exact packet/window/filter/formula and source hashes; stale IDs rejected |
| AC06 | Actual local AI | Fresh end-to-end local LLM run on declared hardware, versioned prompt/schema/digest, raw output and no paid dependency |
| AC07 | Verifier checks rendered meaning | All corrupted-claim fixtures blocked including wrong numbers with valid IDs, wrong periods/units/direction and text-binding mismatch |
| AC08 | Grounded narrative | All required sections, factual evidence links, no fabricated operational capacity or causal assertions |
| AC09 | Measured AI quality | Frozen 40-case protocol, split results and three holdout runs; numerical/citation/abstention/usefulness targets met |
| AC10 | Human review | Named review, rejection, edit-reset, re-verification and revision-bound approval demonstrated |
| AC11 | Export integrity | Approved Markdown/JSON bundle and audit; failed/unapproved draft cannot use approved export |
| AC12 | Failure handling | Empty input, unsupported request, timeout and malformed model output handled visibly; no false approved state |
| AC13 | Zero-cost reproduction | Fresh checkout follows real commands, offline after downloads, exact dependencies, no paid service or trial required |
| AC14 | Team delivery | Separate team repo, access verified, individual contribution evidence, complete handover and final submission |
| AC15 | UAT | Demo cases pass with evidence, limitations disclosed, reviewer sign-off on tagged version |

## Required evidence layout
Store automated results in outputs/evaluations/, attributed demonstration bundles in outputs/examples/ and UAT records in submission/UAT_RESULTS.md. Each record identifies case ID, expected/actual outcome, pass/fail, source/config/code versions and reviewer/date. Do not submit screenshots alone as proof of KPI correctness.

## Definition of done
Every hard gate passes; all known limitations are recorded; final review access is verified; the submitted tag resolves to the evaluated commit. Report runtime targets and business value honestly even when results are modest. No claim of production readiness is required or implied.
