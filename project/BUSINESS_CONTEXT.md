# Business Context — MTL-AI-047

## Simulated operating environment

A commercial mobility operator reviews historical rental activity each week and month. Analysts already calculate operational metrics, but management briefings are prepared manually and vary in clarity, consistency and traceability.

The approved UCI Bike Sharing dataset contains historical aggregate rental observations, weather and calendar context. It does **not** contain station inventory, unmet demand, trip origin/destination, fares, staffing or live-service incidents.

## Business problem

Management needs a consistent explanation of what changed in observed rental activity, which periods were busiest, how user mix changed and where weather/calendar segments are associated with different activity levels.

The risk is that a narrative generator could invent calculations, overstate causality or describe historical rental counts as current operational capacity. The project therefore separates deterministic KPI computation from AI explanation.

## Commissioned decision

> Can a local AI-assisted reporting workflow reduce analyst briefing effort while keeping all numbers, comparisons and evidence under deterministic control?

## Users

| User | Need | Decision supported |
|---|---|---|
| Operations analyst | trustworthy comparisons and evidence | prepare/review briefing |
| Operations manager | concise changes and investigation questions | choose what to investigate next |
| Data lead | governed formulas and source lineage | approve KPI definitions |
| AI/assurance reviewer | verify grounding and failure handling | release or rework the assistant |

## Practical use case

The analyst chooses a reporting period and a valid comparison period. The system first checks data coverage and calculates the agreed KPI package. Only then is the evidence packet passed to the local model.

The generated briefing should cover:

- total observed rentals and change;
- busiest observed hours;
- casual versus registered rental mix;
- selected weather/calendar associations;
- material drivers supported by verified calculations;
- explicit limitations;
- questions that require additional operational data.

The analyst follows evidence IDs, edits unsupported wording, re-runs verification and approves the final management briefing.

## Interpretation boundaries

Observed rental counts are realised historical activity, not unconstrained demand. Busy hours do not prove a shortage. Weather-group differences do not prove causality. Casual/registered counts are rental records, not unique people.

The AI may explain verified metrics but may not invent missing capacity, revenue, staffing, profitability or service-quality facts.

## Value measurement

Compare at least five representative manual briefing tasks against the assisted workflow. Record total preparation time, correction time, number of factual edits, blocked claims and reviewer usefulness. Report sample size and ordering/learning limitations.

A claimed productivity gain is exploratory unless supported by a larger controlled study.
