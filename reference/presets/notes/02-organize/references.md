# Stage 02 — References & Examples

## Vague-task flag examples

| Task | Verdict | Reason |
|---|---|---|
| "Sarah: send deck by Friday" | OK | Owner + date |
| "Someone follow up on budget" | VAGUE — missing: owner | No owner, can't infer |
| "Review legal docs" | VAGUE — missing: owner | No owner stated or implied |
| "Alex: look into options" | VAGUE — missing: clear action | Action is too broad |
| "Team: decide by EOW" | OK if "decide what" is clear from context | Judge by context |

## Grouping example

**Before (flat key points):**
```
KEY-POINT — Launch is Q3
KEY-POINT — Budget approved
KEY-POINT — Marketing needs 2 weeks lead time
KEY-POINT — Design assets due before marketing kickoff
KEY-POINT — Legal sign-off required
```

**After (grouped):**
```
Timeline
  - Launch is Q3
  - Marketing needs 2 weeks lead time
  - Design assets due before marketing kickoff

Resources / approvals
  - Budget approved
  - Legal sign-off required
```

## Deduplication example

Two nearly identical extractions:
```
KEY-POINT — Q3 launch agreed
DECISION  — Q3 launch date confirmed
```
→ Keep: `DECISION — Q3 launch confirmed` and mark `(duplicate KEY-POINT removed)`.
