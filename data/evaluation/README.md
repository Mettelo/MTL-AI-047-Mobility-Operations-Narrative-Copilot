# Evaluation fixtures
Teams curate cases according to [evaluation protocol](../../project/EVALUATION.md). Store versioned case IDs, window/filter configuration, source hashes, independently checked expected metrics, allowed observations, required caveats, prohibited claims and expected abstention/block status.

Keep development and frozen holdout cases separate. Label synthetic/corrupted/injected cases and log their transformations. Never modify holdout gold answers after seeing model outputs without reporting a benchmark revision. This master pack specifies cases and gates; it does not contain completed evaluation results.
