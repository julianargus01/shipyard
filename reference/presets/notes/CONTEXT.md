# Notes Cleaner — Context & Routing

## Input

Pasted raw notes only. Any format: bullet soup, stream of consciousness, transcribed audio, mixed bullet/prose. No file attachments, no URLs to fetch.

## Flow

```
[pasted notes]
     │
     ▼
01-extract    label substance → typed inventory
     │
     ▼
02-organize ★ attach owners/dates, flag vague tasks, group, dedupe
     │           (uses references.md — the judgment stage)
     ▼
03-format     clean recap + optional follow-up draft
```

## Stage read reference

Before running each stage, the AI reads the stage's `rules.md`.
The `★` stage (`02-organize`) also reads `references.md` from the preset root.

| Stage | Files read |
|---|---|
| 01-extract | `01-extract/rules.md` |
| 02-organize | `02-organize/rules.md` + `references.md` |
| 03-format | `03-format/rules.md` |

## What this tool does NOT do

- No external connections.
- No file system access.
- No memory of prior sessions.
- Input must be pasted fresh each run.
