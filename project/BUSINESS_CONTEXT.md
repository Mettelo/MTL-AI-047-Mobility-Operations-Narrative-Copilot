# Business context and decisions

## Operating situation
A hypothetical mobility operator holds aggregate rental records. Analysts already have counts but management briefings vary in speed, clarity and auditability. The copilot drafts a consistent explanation of verified observations while analysts remain accountable for interpretation.

## Decisions supported
| User need | Evidence supplied | Permitted next step |
|---|---|---|
| Understand rental movement | Totals, absolute/percentage change, coverage | Investigate comparable-date patterns |
| Identify busy periods | Counts and mean per observed hour by hour-of-day | Request station and capacity data |
| Understand user mix | Casual/registered rental totals and shares | Investigate service-use patterns |
| Compare conditions | Weather/calendar groups, exposure and means | Explore confounders and further evidence |
| Trust a briefing | Claim IDs, formulas, source hashes, audit | Approve, edit or reject |

## Interpretation boundaries
Observed rentals reflect realised activity; they do not measure unconstrained demand. Busy-hour rankings are system-wide historical observations. There is no station stock, trip duration, trip-level origin/destination, pricing, labour or service incident data in the approved CSVs.

Weather, season, working days, growth between years and hour mix can co-vary. A descriptive group difference cannot establish what caused a movement. Present sample sizes, exposure and a caveat. Never interpret casual/registered counts as unique customer counts.

## Value measurement
Before building, time at least three representative analyst briefing tasks with a deterministic table/template. Repeat with the copilot on the same evidence, recording total preparation plus correction time, number of factual edits and reviewer usefulness (1–5). Declare ordering/learning bias and small sample limitations. Aim for lower preparation effort without weakening correctness; numerical safety gates take priority over speed. Benefits are a hypothesis until measured.

## Stakeholder sign-off
Product owner agrees scope and investigation language; data lead signs metric definitions; AI lead documents model and prompts; QA reviews failures; an analyst reviewer approves exports. Team members may combine roles, but material calculations and final UAT need a second reviewer where a team has multiple members.
