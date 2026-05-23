# Brain-Dump Planner — Context

## Purpose
Three-stage pipeline that processes a raw task/thought dump into a usable daily plan. Each stage does one job; handoffs are explicit.

## Stage map
| Stage | Job | Key file |
|---|---|---|
| 01-capture | Extract and clean atomic tasks from the dump | 01-capture/rules.md |
| 02-score | Rate each task High/Medium/Low on urgency, effort, and impact | 02-score/rules.md + references.md |
| 03-plan | Rank into today's plan + defer list using categorical priority order | 03-plan/rules.md |

## Where judgment lives
`references.md` (root) — defines urgency, effort, impact scales (High/Medium/Low), priority order, daily capacity, and defer rules. Stage 02-score reads it to apply the user's rating system. Stage 03-plan reads it to apply capacity limits, defer rules, and the categorical priority order (no math).

## Input
A single pasted text block — tasks, thoughts, reminders, worries, half-formed ideas. No structure required.

## Output
A ready-to-act daily plan: top-3 tasks for today, a "do later" list, a defer list, and any items flagged as projects-not-tasks.

## Constraints
- Pasted input only; no external reads or API calls
- Stages run sequentially; 01's output feeds 02, 02's output feeds 03
