# MTL-AI-047 — Mobility Operations Narrative Copilot

**Mettelo master project · AI / LLM engineering · Team delivery · £0 core completion**

## The challenge
A bike-sharing operations team can calculate rental KPIs but still spends time turning tables into a management briefing. Build a working local AI product that explains observed rental movements, highlights busy periods, compares weather and calendar segments, and proposes evidence-linked investigation questions.

The product must compute and validate all KPIs in Python/SQL **before** sending a bounded evidence packet to a local LLM. The LLM writes; it does not calculate metrics, query arbitrary data, infer causes, or issue operational commands. A claim verifier checks the draft; an analyst reviews the final version.

This repository is the **challenge specification and project pack**, not a completed application. Teams implement and demonstrate the working product in their own delivery repositories. Example values and acceptance targets are not measured results.

## Business use case
An operations analyst selects a historical reporting window and comparison window, inspects data coverage and verified KPIs, generates a briefing, checks each claim against evidence, edits or rejects it, and exports an approved report with an audit trail. The manager receives an executive summary, rental movement, busy-hour patterns, rider mix, weather/calendar associations, limitations and investigation actions.

Supported questions include:
- How did observed rentals change against the preceding comparable window?
- Which hours had the highest observed rental activity?
- Did casual and registered rental shares differ?
- How did rentals per observed hour vary across weather and working-day segments?
- What should an analyst investigate next, and what evidence is missing?

These are rental records, not unique people, available bicycles, station occupancy, unmet demand, revenue or a live service feed. Do not claim a shortage, staffing requirement, profitability or weather causation from this dataset.

## Free approved data
Use UCI **Bike Sharing**, covering Capital Bikeshare in 2011–2012:
- [Official dataset and dictionary](https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset)
- [Download ZIP](https://archive.ics.uci.edu/static/public/275/bike%2Bsharing%2Bdataset.zip)
- [Dataset DOI](https://doi.org/10.24432/C5W894)
- Licence: CC BY 4.0; credit Hadi Fanaee-T and UCI, link the licence, identify transformations.
- Files: `hour.csv` for primary analysis, `day.csv` for reconciliation, `Readme.txt` for definitions.

UCI lists 17,389 instances. Verify downloaded row counts and hashes rather than assuming the catalogue count equals the CSV count. Do not concatenate hourly and daily records. Full acquisition and interpretation rules: [data guidance](data/README.md).

## Required workflow
```text
Download + hash sources → validate rows and coverage → deterministic KPI engine
→ versioned evidence JSON → local LLM structured draft → claim verification
→ analyst edits + re-verification → human approval → Markdown/JSON export
```

The UI must show the reporting windows, coverage warnings, KPI table, narrative, evidence links, verification results and review status. Invalid data or unsupported windows must stop generation. Unsupported questions receive an explicit insufficient-evidence response.

## £0 delivery route
Use Python, pandas or DuckDB, Pydantic/jsonschema, pytest, Streamlit or a CLI, Git and local files. Use Ollama or llama.cpp with a small open-weight instruction model. A feasible initial candidate is Apache-2.0 Qwen2.5-1.5B-Instruct, available as `qwen2.5:1.5b` in Ollama. Evaluate it; model availability does not imply acceptable performance.

No paid API, cloud hosting, managed database, vector service, GPU purchase, free-trial credit or subscription is required. Use an existing computer; CPU inference is allowed. A deterministic template baseline and replay fixtures support development on limited hardware, but **do not replace a demonstrated local LLM run**. See [local tooling and setup contract](project/LOCAL_TOOLING.md).

## Start here
1. Read the [brief](project/PROJECT_BRIEF.md), [business context](project/BUSINESS_CONTEXT.md) and [deliverables](project/DELIVERABLES.md).
2. Create `MTL-AI-047-<team-name>` and verify [Mettelo review access](submission/TEAM_REPOSITORY_STANDARD.md).
3. Acquire sources following [data/README.md](data/README.md); freeze hashes and definitions.
4. Build and independently check [KPI calculations](project/KPI_SPECIFICATION.md).
5. Implement [evidence, generation and verification](project/AI_WORKFLOW.md), then [human review and governance](project/GOVERNANCE.md).
6. Run the [evaluation protocol](project/EVALUATION.md) and [acceptance checks](project/ACCEPTANCE_CRITERIA.md).
7. Follow the [submission guide](submission/SUBMISSION_GUIDE.md) and complete the [final submission](submission/FINAL_SUBMISSION.md).

## Pack navigation
- [Repository structure](project/REPOSITORY_STRUCTURE.md)
- [Roles and delivery stages](project/TEAM_ROLES.md)
- [Contribution rules](CONTRIBUTIONS.md)
- [Source register](data/SOURCE_REGISTER.md)
- [Raw files](data/raw/README.md) · [Reference material](data/reference/README.md) · [Metadata](data/metadata/README.md)
- [Demo and UAT](project/DEMO_UAT.md)
- [Technical handover](docs/TECHNICAL_HANDOVER.md)

## Completion definition
A reviewer can reproduce the source acquisition, KPI tables, evidence packets, local generation, verification, evaluation and approved export from a clean checkout without paid services. Fluency alone is not success. Numerical correctness, evidence fidelity, appropriate abstention and visible human control are release gates.

**Mettelo — Built for What’s Next**
