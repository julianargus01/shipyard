# 02-score — References

## Example rated table (using default references.md scales)

| # | Task | Urgency | Effort | Impact |
|---|---|---|---|---|
| 1 | Send invoice to client | High | Low | Medium |
| 2 | Review draft blog post | Low | Medium | Medium |
| 3 | Fix login bug on staging | High | Medium | High |
| 4 | Schedule dentist appointment | Low | Low | Low |
| 5 | Write Q2 review | Medium | High | High |

Ratings are categorical (High / Medium / Low). No numeric scores are computed. Priority order is determined in 03-plan.

## Tie-breaking guidance (applied in 03-plan, not here)
When two tasks have the same Urgency, the one with higher Impact ranks first. If still tied, the one with lower Effort ranks first (easier win).

## Urgency signal cues in the user's dump
- Explicit time cues: "by EOD," "today," "this morning," "tomorrow" → Urgency High
- Soft time cues: "this week," "soon," "before Friday" → Urgency Medium
- No time cue, no deadline mentioned → Urgency Low (default)

## PROJECT items
Do not score PROJECT-flagged items. Carry them forward to 03-plan as-is — they go to the "flag" section, not the ranked list.
