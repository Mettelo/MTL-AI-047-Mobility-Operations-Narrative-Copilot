# MTL-AI-047 — Team repository standard

Create **MTL-AI-047-<team-name>** under the **Mettelo GitHub organisation** and add each member using their individual GitHub account.

Record in the team README:

- master repository: https://github.com/Mettelo/MTL-AI-047-Mobility-Operations-Narrative-Copilot
- reviewed master specification commit SHA;
- team members and assigned delivery responsibilities;
- final team commit SHA and release tag;
- approved data/source version and manifest;
- exact setup and run instructions;
- project limitations and simulated-client declaration.

## Required repository structure

```text
README.md
CONTRIBUTIONS.md
.gitignore
requirements.txt or equivalent dependency lock
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

Equivalent tool-specific folders are allowed only when the README provides a clear mapping to this standard. Do not create duplicate implementations simply to match folder names.

## Data handling

Use the approved source described in the master `data/` pack. Where the master already contains an uploaded `data/raw/` file, the team may obtain that approved source from the master or reacquire it from the documented official URL.

The team must still create its own source manifest recording filename, source/version, retrieval or copy date, bytes/hash, licence/terms, parser assumptions and reviewer. Do not treat the presence of a raw file in the master as proof of successful ingestion or validation.

Large raw payloads and model weights should remain outside the team Git repository unless cohort guidance explicitly allows them. `data/raw/README.md` must explain the restore path and expected hash. Never commit credentials or paid-service secrets.

## README and contribution evidence

State the commissioned decision:

> Produce a verified management briefing from deterministic mobility KPIs without allowing the AI to calculate or invent metrics.

Name **Mobility Operations Manager** as the simulated sponsor.

Preserve this interpretation boundary:

> The AI writes from verified evidence only. Historical rental counts do not prove unmet demand, station shortages, revenue, staffing needs or weather causation.

Every member must link:

- substantive artefacts they authored;
- at least one meaningful peer review;
- issues/PRs or equivalent collaboration evidence;
- contribution to UAT, demo or handover.

Commit count alone is not Proof of contribution.

## Required business/product artefacts

- **D5 Verified KPI and evidence packet:** `data/curated/verified-kpi-evidence.json` plus `docs/05-evidence/kpi-evidence-catalogue.md`.
- **D6 AI narrative evaluation:** `docs/06-ai/narrative-evaluation.md` plus `evaluation/results.csv`.
- **D7 Claim-verification policy:** `docs/07-decision-framework/claim-verification-policy.md` plus `tests/claim-fixtures/`.
- **D8 Narrative review product:** `app/README.md` plus `outputs/examples/`.
- **D11 Executive mobility briefing pack:** `deliverables/mobility-briefing-pack.pdf` plus `deliverables/slides/`.

These are default delivery paths. An equivalent format is acceptable only when explicitly mapped in the evidence index.

## Evidence index

Maintain a final D1–D12 / acceptance / test / UAT evidence index with:

- requirement or criterion ID;
- artefact path;
- executed result;
- author;
- distinct reviewer;
- date;
- final state;
- final-commit link.

## Team organisation

Recommended team size: **3–5 people**. Members may combine responsibilities across delivery/business analysis, data governance, engineering, AI, product/interface and assurance. Critical calculations/evaluations and the final clean rerun should be reviewed or executed by a different member where team size permits.
