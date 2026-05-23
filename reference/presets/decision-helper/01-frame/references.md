# 01-frame — References

## Common hidden factors to check for

When reading the pasted input, look for factors the user didn't name but implied:

- **Time horizon** — when does this decision need to be final? When do consequences land?
- **Reversibility** — can this be undone? At what cost?
- **Second-order effects** — who else is affected? What does each option close off?
- **Stated vs. real question** — "should I take job A or B?" might actually be "am I ready to leave my current role?"
- **Missing options** — is there an obvious option the user didn't list (e.g., "do nothing," "do both," "defer")?
- **Constraints assumed but not stated** — budget, time, relationships, obligations

## Format reference

The stage output should be a structured block in this shape:

```
REAL DECISION: [one sentence]

OPTIONS:
  A. [label] — [one-line description]
  B. [label] — [one-line description]
  ...

FACTORS:
  Stated:   [bullet list]
  Surfaced: [bullet list — things inferred from the input]

AMBIGUITIES (if any):
  - [question that, if answered, would materially change the scoring]
```
