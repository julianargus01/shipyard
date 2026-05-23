# Stage 02 — Rules ★

**Read `references.md` before running this stage.**

## Input

The labeled inventory produced by `01-extract`: a flat list of `DECISION`, `TASK`, `KEY-POINT`, `OPEN-Q`, and `NOISE` items.

## Process

1. **Skip `NOISE` items.** Do not carry them forward.
2. **Tasks — attach owners and dates.** For each `TASK`: pull owner and due date from the label. If the raw notes contain context that strongly implies an owner or date not already captured, add it with `(inferred)`. Do not invent.
3. **Tasks — apply the vague-task flag.** Using `references.md` section 2, evaluate each task. If it fails the threshold, append `[VAGUE — missing: <what>]` inline. Do not remove the task — flag it and keep it.
4. **Decisions — check for duplicates.** If two `DECISION` items say the same thing, keep one and note `(duplicate removed)`.
5. **Key points — deduplicate.** Remove near-identical `KEY-POINT` items; keep the clearest version, note `(duplicate removed)`.
6. **Key points — group.** Using `references.md` section 3, group `KEY-POINT` items under theme headers. If fewer than 4 key points remain, list flat (no grouping needed).
7. **Open questions — keep all.** Do not drop, merge, or reframe `OPEN-Q` items unless two are truly identical.
8. **Do not rephrase decisions or tasks** beyond what is needed to make them grammatically complete.

## Output

Four organized sections:

```
## Decisions
1. <decision>
2. <decision>

## Tasks
| Task | Owner | Due | Flags |
|---|---|---|---|
| <task> | <owner or TBD> | <date or —> | [VAGUE — missing: X] or — |

## Key Points
### <Theme>
- <point>
- <point>

### <Theme>
- <point>

## Open Questions
- <question>
- <question>
```

## Gate

Pass to `03-format` when:
- Every `TASK` has an Owner and Due column entry (even if `TBD` or `—`).
- Every task that meets the vague threshold in `references.md` has a `VAGUE` flag.
- No `KEY-POINT` items are ungrouped (unless fewer than 4 total).
- No `NOISE` items appear in the output.
- No decisions or tasks were dropped — only flagged or deduplicated.
