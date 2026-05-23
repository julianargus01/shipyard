# Phase 4 Reference

## Stage File Quality (ICM)

Each workflow stage gets its own folder. Each stage folder contains `context.md`, `rules.md`, and `references.md`.

The stage folder is the unit of build. Do not collapse the workflow into one behavior file.

### Stage Contract Test

Every stage must answer four questions:

| Section | Question | Passes when |
|---------|----------|-------------|
| Input | What does this stage receive? | The input comes from the user or the previous stage |
| Process | What does this stage do? | The process is one stage's job, not the whole project |
| Output | What does this stage pass forward? | The output is concrete enough for the next stage to use |
| Gate | What must be true before the next stage starts? | The gate is observable |

If a different AI read only this stage folder, it should know what this stage receives, does, outputs, and checks before handing off.

### One-Stage Test

For each stage: "If a different AI read only this stage folder, would it run this stage correctly without knowing the whole project?"

If the answer is no, the stage is too vague or doing too much.

### What Makes Stage Rules Work

- **One stage, one job.** "Extract repeated tasks and time costs" — not "audit the workflow."
- **Action, not description.** "List every repeated task mentioned" — not "analyze the workflow."
- **Explicit handoff.** "Output a list of evidence fields for 02-diagnose" — not "prepare the results."
- **Concrete gate.** "Proceed only when at least one repeated task and one friction signal are present" — not "when it seems ready."
- **Criteria where judgment happens.** "Use criteria.md before choosing" — not "pick the best one."

### Stage Folder Minimum

Every stage folder must contain:

| File | What goes in it | How to check it |
|------|----------------|-----------------|
| `context.md` | Stage routing map: input, files to read, output, gate | Has Input, Routing, Output, Gate |
| `rules.md` | Step-by-step instructions for this stage only | Applies the one-stage test |
| `references.md` | Examples, criteria pointers, source material, or "No extra references for this stage" | Does not contain the stage process |

### Criteria File Minimum

Use root `criteria.md` if any stage chooses, diagnoses, ranks, screens, recommends, prioritizes, or decides.

It must include:
- evidence fields
- decision criteria
- disqualifiers
- missing-info behavior

Judgment stages must point to `../criteria.md` or root `criteria.md` in their stage files.

### Stage Handoff Test

After stage files are written, run the workflow in order.

For each handoff:
1. Run the stage using realistic input.
2. Name the stage output.
3. Ask: "Does the next stage have enough to do its job?"
4. If not, tighten the first stage's output or the next stage's input.

The project passes only when every stage output feeds the next stage.

### Common Failures

| Failure | Why it fails | Fixed version |
|---------|-------------|---------------|
| One catch-all file | It is a prompt, not a staged workflow | Split into stage folders |
| "Analyze the workflow" | AI can interpret "analyze" 50 ways | "List repeated tasks, time costs, waiting points, and manual re-entry" |
| "Find the pain point" | No criterion for choosing | "Use criteria.md to choose the pain point with highest recurring time cost or coordination friction" |
| "Suggest AI tools" | Produces a spray of options | "Recommend one AI tool that directly addresses the diagnosed pain point" |
| No gate | Stage can pass bad output forward | "Proceed only when [observable condition] is true" |

## Three Types of Stuck

### Type 1 — Knowledge Gap
Don't know what to do next.
→ Teach the minimum to unlock the next step. One concept, one sentence.
→ Hand rep back: "Now you try it."

### Type 2 — Decision Paralysis
Too many options.
→ Pick for them: "Go with [A]. Here's why in one sentence. Try it."
→ Iteration beats deliberation.

### Type 3 — Fear / Avoidance
Know what to do, won't do it.
→ Name it: "It sounds like you know the next step. What's actually stopping you?"
→ Redirect to the smallest possible version of the scary action.
→ If stalling on shipping: move to Phase 5.

## Never
- Give a list of options and ask them to choose — that's more paralysis
- Explain the full system when they need one next step
- Let a debugging spiral eat the session — "Try one thing for 15 minutes. If it's still broken, show me what you tried."
