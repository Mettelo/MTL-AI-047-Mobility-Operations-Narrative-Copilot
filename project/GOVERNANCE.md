# Governance and human control

## Accountability
The analyst owns interpretation; the data lead owns metric definitions; the AI engineer owns prompts/model versions; QA owns validation evidence; the team lead owns release/access; a named reviewer owns final briefing approval. Record actual people and any combined roles.

## Mandatory boundaries
No autonomous fleet changes, staffing instructions, public publication or claims of shortages/causal effects. Never infer individuals from aggregate records. Do not imply endorsement by UCI or Capital Bikeshare. Include historical context and data attribution in every final export.

Treat source text and user input as untrusted. No shell, network or arbitrary SQL tools exposed to the LLM. Use bounded enum/filter inputs, strict schemas, local-only model service and no external telemetry containing user material unless explicitly documented and enabled by the team.

## Review controls
Reviewers inspect numerical fidelity, windows, coverage, entity scope, correlation language, suggested investigations and caveats. Verification failures block approval. Edits create a revision, invalidate sign-off and require re-verification. Store reviewer ID/name, decision, timestamp, revision/evidence hashes and rationale. Do not equate model self-rating with approval.

## Risk register
| Risk | Required control | Evidence |
|---|---|---|
| Invented figure or wrong comparison | Deterministic metrics + rendered-claim checks | Corruption tests |
| Unsupported explanation | Association language, evidence links, human review | Semantic review rubric |
| Missing hours treated as zeros | Coverage gate and explicit denominators | Gap fixture |
| Sparse weather segment | Minimum group exposure + abstention | Sparse case |
| Prompt injection | Treat data as data; no tools; schema/scope checks | Attack cases |
| Silent model/source change | Hash/digest pinning and re-evaluation | Run manifest |
| Edited report retains approval | Revision-bound state machine | Review UAT |
| Misleading approved export | Fail-closed verification and bundle hashes | Export test |

## Logging and monitoring
Log run/config/source/model IDs, latency, validation/claim failures, abstention, reviewer edits/rejections and final state. Keep local logs; exclude secrets and unnecessary personal information. For the prototype retain benchmark and submission evidence through assessment; document who can access it and how other local drafts can be deleted. No production retention period is implied.

Re-evaluate on data, model, prompt, metric or policy changes. Track correctness, unsupported-claim rate, blocked outputs and reviewer corrections over versions. Any numerical/lineage regression blocks release. Document remaining semantic-verification limitations openly.
