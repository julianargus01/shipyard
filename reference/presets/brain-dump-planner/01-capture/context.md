# 01-capture — Context

## Role in the pipeline
First stage. Receives the raw user dump and produces a clean, numbered list of atomic tasks. Nothing is scored or ranked here — the only job is cleaning and extracting.

## What "atomic" means
One task = one clear, do-able action. "Write report and email Sarah" is two tasks. "Think about the project" is noise unless it becomes "Decide X by [date]."

## What gets dropped at this stage
- Pure thoughts with no action (keep only if they can be made actionable)
- Exact duplicates
- Filler phrases ("I should probably...", "maybe...")

## Handoff
Output of this stage is the exact input for 02-score. Format matters — 02-score expects a numbered list.
