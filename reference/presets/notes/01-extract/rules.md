# Stage 01 — Rules

## Input

Raw pasted notes: any format (bullets, prose, transcription, mixed). No preprocessing assumed.

## Process

1. Read the full notes top-to-bottom once before labeling anything.
2. For each distinct statement or fragment, assign exactly one label: `DECISION`, `TASK`, `KEY-POINT`, `OPEN-Q`, or `NOISE`.
3. Use `references.md` section 1 (action-vs-note rule) to distinguish `TASK` from `KEY-POINT`.
4. For `TASK` items: note any owner or date stated or strongly implied in the raw text. Do not invent.
5. Label `NOISE` only for fragments with no recoverable substance (e.g., "um", "anyway", off-topic small talk).
6. Preserve original phrasing where possible — do not paraphrase at this stage.
7. Output every labeled item, including `NOISE` (marked so the next stage can skip them cleanly).

## Output

A flat labeled inventory. Format:

```
DECISION  — <statement>
TASK      — <statement> [owner: <name or TBD>] [due: <date or none stated>]
KEY-POINT — <statement>
OPEN-Q    — <question>
NOISE     — <fragment>
```

One item per line. No grouping. No deduplication. No editorializing.

## Gate

Pass to `02-organize` when:
- Every fragment of the input has a label.
- No `TASK` item is missing its owner/due notation (even if the notation is `TBD` / `none stated`).
- No interpretation has been added beyond labeling.
