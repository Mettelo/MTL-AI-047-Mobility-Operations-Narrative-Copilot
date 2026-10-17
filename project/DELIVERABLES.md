# Required deliverables

| ID | Deliverable | Minimum content | Acceptance link |
|---|---|---|---|
| D01 | Problem and scope | Users, reporting decisions, workflow, boundaries and value baseline | AC08, AC15 |
| D02 | Source and data pack | Register, dictionary, immutable download workflow, hashes, licence, coverage and daily reconciliation | AC01–04 |
| D03 | KPI engine | Reusable deterministic modules, formula catalogue, independent gold fixtures, window/filter policies | AC03–04 |
| D04 | Evidence contract | Versioned schema, stable IDs, packet hash, metric units/periods/denominators/lineage and caveats | AC05 |
| D05 | Local AI generation | Local model configuration, prompt versions, structured output, baseline comparison and fresh recorded run | AC06, AC08 |
| D06 | Claim verifier | Schema, IDs, numerical/text/semantic-scope checks, failure reasons and corrupt-claim tests | AC07 |
| D07 | Working review product | Report controls, evidence drilldown, edit/reject/approve, revision audit, approved export | AC10–12 |
| D08 | Evaluation pack | 40 cases, gold evidence, development/holdout separation, repeated results, human scores and failure analysis | AC09 |
| D09 | Governance | Risk register, injection tests, access/logging rules, limitations and accountable owners | AC02, AC08, AC12 |
| D10 | Handover and submission | Setup commands, locked versions, tests, UAT, demo, cost declaration, contribution links, final tag | AC13–15 |

## Evidence expected from every team
Commit code and documentation, not only slides. Include at least three end-to-end example bundles: a valid approved report, an insufficient-evidence response and a blocked invalid claim. Include one weather association with caveats and one report with an analyst revision, either within these examples or as additional bundles.

Exploratory notebooks are allowed, but the core data/KPI/generation/verification logic must run from reusable modules. Screenshots and a short demo aid review; they do not replace executable code, source provenance or recorded evaluations.
