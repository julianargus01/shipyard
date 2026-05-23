# Stage 01 — References & Examples

## Category labels

| Label | Meaning |
|---|---|
| `DECISION` | Something resolved, agreed, or chosen |
| `TASK` | Something someone needs to do |
| `KEY-POINT` | Observation, fact, or context worth keeping |
| `OPEN-Q` | Unanswered question needing a future response |
| `NOISE` | Filler, off-topic tangent, or clearly irrelevant fragment |

## Example extraction

**Raw input fragment:**
> "ok so we agreed on the Q3 launch, Sarah's handling the deck, not sure who does legal review yet, also was that budget thing resolved?"

**Extracted inventory:**
```
DECISION — Q3 launch agreed
TASK     — Sarah: handle deck [owner: Sarah, date: none stated]
TASK     — Legal review [owner: TBD]
OPEN-Q   — Budget thing — resolved?
```

## Edge case: repeated items

Extract all instances. Do not dedupe at this stage — that is `02-organize`'s job.
