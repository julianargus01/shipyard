# 03-plan — Context

## Role in the pipeline
Final stage. Takes the rated task table from 02-score and produces a concrete, ready-to-act daily plan. No new rating — only ranking and bucketing using the categorical ratings (High/Medium/Low) and capacity rules from `references.md`.

## What this stage does
- Selects the top-3 tasks for today (applying urgency overrides and capacity limits)
- Puts the rest into a "do later" list
- Moves low-score items to a defer list
- Surfaces any PROJECT flags separately
- Flags any top-3 that are actually projects-not-tasks (shouldn't reach here, but catches slippage)

## Key dependency
Read `references.md` for daily capacity limits, defer rules, and priority order (categorical — no math). Do not rank arbitrarily.

## Handoff
This is the terminal stage. Output is handed directly to the user — it must be immediately actionable.
