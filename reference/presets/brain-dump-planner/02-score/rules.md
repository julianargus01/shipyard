# 02-score — Rules

## Input
Numbered task list from 01-capture (atomic tasks + any PROJECT flags).

## Process
1. Read `references.md` (root) before rating. Use its urgency, effort, and impact definitions exactly.
2. For each task (not PROJECT items), assign a categorical rating:
   - **Urgency** (High / Medium / Low): scan the task text for time cues, deadlines, or blocking signals; default to Low if none present.
   - **Effort** (High / Medium / Low): estimate based on the task description and references.md effort levels.
   - **Impact** (High / Medium / Low): assess value against references.md impact levels.
3. Do NOT compute a numeric score. The priority order is determined in 03-plan using the categorical ratings.
4. Do not rate PROJECT-flagged items — carry them as-is to the output.
5. Note a one-line reason for any rating you expect the user might question (optional but helpful for High-effort or Low-urgency items).

## Output
A scored table plus the PROJECT list unchanged.

Format:
```
## Rated Tasks
| # | Task | Urgency | Effort | Impact |
|---|---|---|---|---|
| 1 | [task text] | H/M/L | H/M/L | H/M/L |
...

## Projects (not rated)
- PROJECT: [name]
```

## Gate
Every task has all three categorical ratings filled (Urgency, Effort, Impact — each is High, Medium, or Low). No numeric scores computed. No tasks invented or dropped from 01-capture output. PROJECT items are present and unmodified.
