# MTL-AI-047 — Team repository standard

Create **MTL-AI-047-<team-name>** under the **Mettelo GitHub organisation** and add individual member accounts.

Record in the team README: master URL and reviewed commit, members/roles, approved source/hash, environment/run instructions, final team SHA/tag and project limitations.

## Required repository structure

```text
README.md
CONTRIBUTIONS.md
.gitignore
requirements.txt or equivalent lock
config/
src/
app/
tests/
prompts/
evaluation/
outputs/
data/
  SOURCE_REGISTER.md
  raw/
    README.md
  reference/
  metadata/
  curated/
docs/
  01-discovery/
  02-data-governance/
  03-data-model/
  04-data-quality/
  05-evidence/
  06-ai/
  07-decision-framework/
  08-assurance-uat/
  09-technical-handover/
deliverables/
submission/
  FINAL_SUBMISSION.md
```

Equivalent tool-specific folders are allowed only with a documented mapping.

## Data handling

Use the approved UCI Bike Sharing source in the master. The team may copy the approved raw ZIP from master `data/raw/` or reacquire it from the official source, then record its own source manifest with filename, version, retrieval/copy date, bytes/hash, licence, parsing rules and reviewer.

The raw ZIP appearing in the master is not proof that the team has validated the source. Keep large raw payloads/model weights outside the team repo unless cohort guidance explicitly permits them.

## README and contribution evidence

State:

> Produce a verified management briefing from deterministic mobility KPIs without allowing the AI to calculate or invent metrics.

Simulated sponsor: **Mobility Operations Manager**.

Preserve this limitation:

> The AI writes from verified evidence only. Historical rental counts do not prove unmet demand, station shortages, revenue, staffing needs or weather causation.

Every member links authored artefacts, at least one substantive peer review, and demo/UAT/handover contribution. Commit count alone is not Proof.

## Required project-specific artefacts

- **D5 Verified KPI/evidence packet:** `data/curated/verified-kpi-evidence.json` and `docs/05-evidence/kpi-evidence-catalogue.md`.
- **D6 AI narrative evaluation:** `docs/06-ai/narrative-evaluation.md` and `evaluation/results.csv`.
- **D7 Claim-verification policy:** `docs/07-decision-framework/claim-verification-policy.md` plus corrupted-claim fixtures/tests.
- **D8 Narrative review product:** `app/README.md` and `outputs/examples/`.
- **D11 Executive mobility briefing pack:** `deliverables/mobility-briefing-pack.pdf` plus editable slides.

Maintain D1–D12 / acceptance / test / UAT evidence with owner, distinct reviewer, result/state and final-commit link.

Recommended team size: **3–5 people**.
