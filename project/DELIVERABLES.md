# Deliverables — MTL-AI-047

All paths refer to the team delivery repository. Every deliverable records an owner, reviewer, evidence link, status and revision date.

| ID | Required output | Minimum evidence | Default location |
|---|---|---|---|
| D1 | Discovery & reporting workflow | users; as-is/to-be process; ≥8 requirements; scope; stakeholder map; acceptance mapping | docs/01-discovery/ |
| D2 | Source & governance pack | UCI source/DOI/licence; hashes; data dictionary; coverage; exclusions; attribution | docs/02-data-governance/ + data/SOURCE_REGISTER.md |
| D3 | Reproducible analytical model | ingestion; hourly/daily grain controls; validation; canonical dates/hours; reusable modules | src/ + docs/03-data-model/ |
| D4 | KPI & comparison catalogue | formula, period, unit, denominator, filters, coverage policy, zero-baseline handling | docs/04-kpi-catalogue/ |
| D5 | Deterministic evidence engine | verified KPI JSON/evidence packet; stable IDs; source/period/filter lineage; materiality logic | docs/05-evidence/ + outputs/ |
| D6 | Local AI narrative layer | pinned local model/runtime; prompt/schema; raw generations; deterministic fallback | prompts/ + docs/06-ai/ |
| D7 | Claim verification & guardrails | numeric, period, direction, unit, evidence-ID and unsupported-causality checks | tests/ + docs/07-guardrails/ |
| D8 | Working review product | period selection; KPI view; narrative; evidence drill-down; edit/reject/approve; export audit | app/ + outputs/examples/ |
| D9 | Evaluation & assurance | frozen 40-case protocol; dev/holdout separation; repeated runs; metrics; failure analysis | evaluation/ |
| D10 | UAT & technical handover | ≥10 domain tests; 3 user tasks; defects/retests; exact setup/run/restore/troubleshooting | docs/08-assurance-uat/ + docs/09-technical-handover/ |
| D11 | Executive recommendation & demo | 2-page decision brief; 8–12 slides; live/reproducible demo; retain/revise/pilot recommendation | deliverables/ |
| D12 | Final submission & contributions | final SHA/tag; evidence index; CONTRIBUTIONS.md; individual artefacts/reviews; limitations | submission/ + CONTRIBUTIONS.md |

## Required demonstration

Show one valid comparison window, one low-coverage/invalid window that blocks generation, one verified narrative with traceable metrics, one deliberately corrupted claim rejected by the verifier, one analyst edit that requires re-verification and one approved export.

A dashboard or fluent narrative without deterministic metric evidence does not complete the project.
