# 02-score — Context

## Role in the pipeline
Second stage. Takes the numbered task list from 01-capture and rates each item (High / Medium / Low on urgency, effort, and impact) using the rules in `references.md` (root level). This is the judgment stage — the user's rating rules are applied here.

## What this stage does NOT do
- Does not rank or plan — that is 03-plan's job
- Does not add new tasks or remove items (01-capture already cleaned the list)
- Does not override urgency — if the user marked something urgent in their dump, preserve that signal

## Key dependency
Read `references.md` before rating. All rating definitions (urgency, effort, impact, and priority order) come from there. Do not invent scales or compute numeric scores.

## Handoff
Output is a rated table (High/Medium/Low per factor). 03-plan uses the categorical ratings to rank and bucket items into today's plan.
