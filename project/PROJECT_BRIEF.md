# Project brief

## Objective and users
Deliver an operational briefing copilot for a simulated bike-sharing reporting team using historical Capital Bikeshare records. Primary user: operations analyst preparing a weekly briefing. Secondary user: manager reviewing patterns and deciding which investigations need further data. Reviewer: Mettelo assessor checking reproducibility and AI reliability.

The problem is the manual translation of verified metrics into a traceable narrative. The product must offer more than a dashboard, notebook, generic chat interface or static report.

## Core product journey
1. Load the approved local dataset and display source identity/hash and date range.
2. Validate schema, rental identities, date/hour uniqueness and completeness.
3. Select a report window and a non-overlapping comparison window; show exact dates and exclusions.
4. Calculate KPIs and coverage deterministically; expose formulas and segment sizes.
5. Create an immutable evidence packet with stable IDs, definitions and caveats.
6. Generate a bounded structured narrative using a local model.
7. Check every factual claim and surface failures beside its evidence.
8. Allow edits, rejection and re-generation. Any edit invalidates previous approval.
9. Re-verify the edited report; obtain named human sign-off.
10. Export report, evidence, claim results and review audit together.

## Minimum narrative sections
- Executive summary of observed rental movements.
- Current/comparison total and percentage movement, or reason a comparison is unavailable.
- Busy-hour profile, working-day patterns and rider-type mix.
- Weather/season associations with exposure/sample caveats.
- Evidence-linked investigation questions, missing information and limitations.

Each section may explicitly abstain if evidence is insufficient. Keep observations, hypotheses and suggested investigations visibly distinct. Recommendations must be reversible investigation steps; do not prescribe fleet movements or staffing as established requirements.

## Core scope
Historical reporting only; validated UCI inputs; configurable periods; deterministic descriptive metrics; local inference; structured claims; verification; human review; accessible local interface; Markdown and JSON exports; repeatable tests and evaluation.

## Out of scope
Demand forecasting, dispatch optimisation, station-level availability, live APIs, revenue/cost inference, causal inference, individual rider profiling, autonomous publication, fine-tuning and paid infrastructure. Optional extensions cannot compensate for missing core requirements.

## Required scenarios
Ordinary weekly comparison; seasonal comparison; working-day versus non-working-day; weather segments with unequal exposure; sparse severe-weather group; missing hours; corrupted rental totals; empty period; zero baseline; prompt injection; invented evidence ID; changed number; changed direction; model unavailable; reviewer edits after approval.

Use actual source windows where available. Controlled faults and synthetic edge cases must be labelled, isolated from raw files and accompanied by a transformation log. Never pass injected values off as historical facts.

## Delivery stages
1. Scope, role allocation, source/licence review, laptop feasibility check.
2. Validated ingestion, coverage audit and independently reconciled metrics.
3. Baseline briefing, local AI draft, claims and verifier.
4. Interface, approval workflow, exports and adversarial tests.
5. Frozen evaluation, UAT, clean-machine reproduction and handover.

Teams agree dates and owners in their issue board. Each stage has reviewed evidence before proceeding; no fixed cohort duration is assumed.

## Outcomes
Measure briefing preparation time against a template/manual baseline using the same tasks; record factual correction rate, traceability, reviewer usefulness and abstention behaviour. Report measured outcomes and limitations, never invented productivity savings. The acceptance gates are in [ACCEPTANCE_CRITERIA.md](ACCEPTANCE_CRITERIA.md).
