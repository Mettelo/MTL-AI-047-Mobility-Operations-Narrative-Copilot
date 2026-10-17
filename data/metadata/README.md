# Metadata and lineage
Implement source_manifest.json plus validation_report.json and a versioned data_dictionary.json.

The source manifest needs one entry per archive/extracted file: source ID, URL, retrieval UTC, filename/path, bytes, SHA-256, licence/citation, row count, columns, grain and date range. Populate real values after acquisition; missing values remain explicitly pending, not fabricated.

Validation report: schema version, input hashes, duplicate/null/invalid counts, missing-hour keys, per-day reconciliation results, disposition, author and review date. Distinguish source facts from project reporting policies.

Each derived table/evidence packet records input hashes, code commit, config hash, filters/windows, formulas, policy versions and creation time. Hash canonical serialised evidence; document canonicalisation. Link report revisions and approval records to this hash. Retain enough selection metadata to reproduce each aggregate without copying raw rows into prompts.
