# Mandatory team repository structure

Create one delivery repository: `MTL-AI-047-<team-name>`. This Mettelo master repository holds the specification; teams supply their implementation and results.

```text
README.md
CONTRIBUTIONS.md
.gitignore
.env.example
requirements.txt (or pyproject.toml + dependency lock)
project/             # specification and team decisions
config/              # versioned metric, coverage and model settings
data/
  raw/               # local immutable sources, download guidance
  reference/         # source dictionary and licences
  metadata/          # manifests, hashes and validation reports
  processed/         # reproducible derived tables/evidence
  evaluation/        # development and holdout fixtures
docs/
  business/          # decisions, user workflow and value measurement
  architecture/      # contracts, lineage and state transitions
  evaluation/        # protocol, results and failure analysis
  governance/        # risks, approvals and model/data limitations
  handover/          # real setup/run/troubleshooting commands
src/
  ingestion/
  validation/
  metrics/
  evidence/
  generation/
  verification/
  review/
  export/
app/
tests/
notebooks/           # optional exploration only
outputs/
  examples/
  evaluations/
submission/
  TEAM_REPOSITORY_STANDARD.md
  SUBMISSION_GUIDE.md
  FINAL_SUBMISSION.md
  UAT_RESULTS.md
```

Each directory needs real artifacts or a README describing its responsibility and rebuild route. Put reusable business logic under src/, not inside UI callbacks or notebooks. Keep prompts and schema definitions versioned alongside the responsible module/config.

Exclude virtual environments, credentials, model weights, caches, raw downloads and large generated data. Include small attributed reproducible examples and benchmark results. Maintain relative document links. Freeze the final reviewed implementation using `v1.0-mettelo-submission`; do not move the tag silently.
