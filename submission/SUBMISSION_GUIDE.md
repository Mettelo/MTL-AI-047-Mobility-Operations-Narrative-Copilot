# Submission guide

1. Create the separate team repository and add members with individual accounts. Read [repository standard](TEAM_REPOSITORY_STANDARD.md).
2. Name owners and dates for deliverables. Use issues, branches, meaningful commits and reviews during development.
3. Verify Mettelo access through the designated cohort route and record evidence.
4. Finish every [deliverable](../project/DELIVERABLES.md). Replace generic instructions in the team README with real, tested application commands.
5. Freeze data hashes, metric definitions, prompts, model digest, configuration and benchmark version.
6. Run automated checks and the 40-case evaluation; retain raw runs and failure analysis. Never replace failed runs with cherry-picked examples.
7. Complete [UAT/demo](../project/DEMO_UAT.md), including a fresh local model run, blocked bad claim and approval-reset demonstration.
8. Have a reviewer follow setup from a clean checkout. Confirm no paid dependency and offline operation after initial downloads.
9. Complete [FINAL_SUBMISSION.md](FINAL_SUBMISSION.md) with real links, actual results, limitations, contribution records and the acceptance matrix.
10. Commit final evidence, then tag the evaluated commit `v1.0-mettelo-submission`. Record the commit SHA and tag in the submission. Submit the team repository URL through the cohort channel; do not send project files by email.
11. Keep reviewer access active until assessment/sign-off. If fixes follow submission, identify a new version and rerun affected checks; do not silently move an assessed tag.

## Final QA
- [ ] Source manifests, licences, attribution and hashes are real.
- [ ] Data/KPI checks pass; AI does not compute metrics.
- [ ] Claims and rendered text verify against the correct evidence packet.
- [ ] Unsupported requests and invalid data block or abstain correctly.
- [ ] Edits invalidate approval; approved exports carry review/evidence hashes.
- [ ] AI evaluation denominators, raw failures and human scores are available.
- [ ] Local model run, setup reproduction and zero-cost path are demonstrated.
- [ ] All members' work and peer review are visible.
- [ ] Mettelo access is verified; final tag points to evaluated code.
- [ ] Final submission contains no unexplained placeholders or unsupported performance claims.
