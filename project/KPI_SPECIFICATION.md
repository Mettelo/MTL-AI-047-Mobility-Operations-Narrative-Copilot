# Deterministic KPI and comparison specification

## Input contract
Primary grain: one row per source date and hour from hour.csv. Key: (dteday, hr). Preserve instant as a source identifier. Treat timestamps as source-local labels; do not invent UTC offsets or daylight-saving repairs. Parse dates strictly; enforce hr 0–23, nonnegative integer cnt/casual/registered, cnt = casual + registered, valid documented category codes and finite numeric measurements.

Reject duplicate keys, malformed required fields and broken rental identities before generation. Do not silently drop faults. Missing rows differ from null cells: UCI's no-missing-values description does not imply a complete hourly grid.

## Window and exposure rules
Use inclusive calendar dates and display them. Default: a chosen Monday–Sunday week versus the immediately preceding Monday–Sunday week. Both must lie inside source coverage. Custom non-overlapping equal-duration windows are allowed with explicit warnings for unequal weekday/holiday composition.

Expected exposure = calendar days × 24 nominal hourly slots. Observed exposure = unique valid date/hour keys. Coverage = observed/expected × 100. This is a source-grid completeness diagnostic, not proof of operating availability. Never fill absent hours with zero by default. Display missing slots and denominator policy.

For core comparisons require at least 95% nominal coverage in each window and equal calendar duration; otherwise show descriptive available observations and suppress percentage-change conclusions. Do not silently shorten windows to valid rows. This threshold is a project policy, not a UCI definition.

## Metric catalogue
| ID family | Definition | Units / denominator |
|---|---|---|
| rentals.total | sum(cnt) for valid selected rows | rentals, integer |
| rentals.casual / registered | sum corresponding count | rentals |
| mix.casual / registered | 100 × segment rentals / total | percent; null if total=0 |
| rentals.delta | current total − comparison total | rentals |
| rentals.pct_change | 100 × (current−comparison)/comparison | percent; null if baseline=0 or comparison invalid |
| exposure.observed / expected | unique keys / nominal grid size | hours |
| exposure.coverage | 100 × observed/expected | percent |
| rentals.per_observed_hour | sum(cnt)/observed keys | rentals per observed hour |
| profile.hour | per hr: sum(cnt), number of observed rows, mean(cnt) | rentals and rentals/observed hour |
| profile.peak_hour | hr with highest mean(cnt) | show all tied hours; do not choose arbitrarily |
| segment.workingday | totals, observed rows, mean(cnt), shares by code | explicit exposure |
| segment.weather / season | same aggregates by documented code | explicit exposure and group size |

All metric IDs must include window and filter context in evidence. Compute both total and exposure-normalised differences for group discussion. Do not compare weather totals as if exposures were equal. Suppress generalised group interpretation when fewer than 30 observed hourly rows; retain counts and label insufficient evidence. This minimum is a configurable, versioned reporting policy.

## Precision and verification
Retain full precision in evidence; render integer counts exactly and percentages/means to one decimal using a documented rounding convention. The verifier compares against deterministic formatted values at that precision; it must distinguish percentage points (current share − baseline share) from percent change. Never let the LLM calculate either.

## Reconciliation
Group hourly counts by dteday and compare cnt, casual and registered with day.csv. Report every mismatch and investigate before sign-off; never add the two files. Do not assert daily weather/temperature fields equal simple hourly means without checking source definitions. A reviewer independently recomputes at least one complete window and three segment groups using separate SQL, spreadsheet or hand calculations.

## Tests required
Exact fixture totals, rider identity, denominator zero, zero-to-positive baseline, equal values, decline direction, rounding boundaries, tied peaks, unequal segment exposure, sparse groups, duplicate keys, missing grid slots, invalid codes, non-overlap and window bounds. Tests should assert expected values fixed independently of the implementation.
