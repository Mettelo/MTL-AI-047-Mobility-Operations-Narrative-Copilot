# Derived data
Write validated hourly tables, reconciliation summaries, deterministic KPI tables and evidence packets here. Keep the raw source immutable. Each artifact must carry source hashes, transform/code version and configuration.

Never mix daily and hourly counts, silently impute missing hours, or include test perturbations in historical outputs. Large rebuildable files may stay untracked. Commit a small attributed example packet and a documented rebuild route in the team delivery.
