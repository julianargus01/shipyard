# Phase 3 Reference

## Scoping the Project

### The Two-Question Test
1. **Does it do the one thing?** One job. If done, it's shippable.
2. **Can someone else use it right now?** Not "will they want to" — can they access it today?

Both yes = done. Ship it.

### Definition of Done Template
Fill in with the user — written, not verbal:

> "This project is done when: [one sentence — minimum working state].
> I'll know it worked when: [specific observable outcome]."

Example:
> "Done when a restaurant owner can paste a Google review and get a draft response back.
> I'll know it worked when my uncle says 'yeah, I'd use that.'"

### The Cutting Rule
For every feature: "Is this the one thing, or is this extra?"
- The one thing → keep it
- Everything else → V2 list

## Workflow Model

Shipyard projects are workflow projects. They are not single prompt files.

Every project must be broken into at least three workflow stages:

1. **Intake:** get the right input.
2. **Work:** do the project-specific processing.
3. **Output:** return the useful result.

Many projects need more than three stages. Use as many as the workflow needs, but never fewer than three.

Lock these before building:
1. **Input:** what starts the workflow?
2. **Stages:** what named stages does the workflow run, in order?
3. **Handoffs:** what does each stage pass to the next stage?
4. **Output:** what does the final stage return?

### Stage Contract

Every stage folder follows the same contract:

```
## Input
What this stage receives.

## Process
What this stage does.

## Output
What this stage passes forward.

## Gate
What must be true before the next stage starts.
```

If any stage chooses, diagnoses, ranks, screens, recommends, prioritizes, or decides what matters, that stage must use criteria.

## Playbook Structure

### The Problem the Playbook Solves
Every time you open an AI, it starts from zero. The folder fixes that — the AI reads your files and knows your context before you say a word.

### Required Root Structure

Every Shipyard build has root files and stage folders:

| File or folder | What goes in it | Read this |
|------|----------------|-----------|
| `AGENTS.md` | Who the AI is. Two fields: identity line ("You are [X].") and job line ("Your job is [Y].") | ### AGENTS.md Template |
| `CONTEXT.md` | Root routing map: what the project does and which stage folder starts each part of the workflow | ### Example Root CONTEXT.md |
| `[stage-folder]/` | One folder per workflow stage. Minimum three stage folders. | ### Stage Folder Structure |
| `criteria.md` | Decision criteria used by any stage that chooses, diagnoses, ranks, screens, recommends, prioritizes, or decides | When judgment exists |

### AGENTS.md Template
```
You are [name or role].
Your job is to [one sentence — what you do for the user].
```

### CONTEXT.md Is Always a Routing Map
Steps and content live in stage folders. Root CONTEXT.md points to the workflow stages — never a flat instructions dump.

### Example Root CONTEXT.md
```
## What This Project Does
[One sentence]

## Workflow Routing
| Stage | Read this |
|------|-----------|
| 01-intake | 01-intake/context.md |
| 02-process | 02-process/context.md |
| 03-output | 03-output/context.md |
```

### Stage Folder Structure

Each stage gets its own folder. Each stage folder has the same minimum ICM structure:

```
[stage-folder]/
  context.md
  rules.md
  references.md
```

| File | Job |
|------|-----|
| `context.md` | Routing map for this stage: what this stage receives, what files it uses, and what it outputs |
| `rules.md` | Step-by-step instructions for this stage only |
| `references.md` | Examples, criteria, source material, or "No extra references for this stage" |

### Criteria File

Use root `criteria.md` when any stage makes a judgment.

Judgment signals:
- chooses
- diagnoses
- recommends
- ranks
- screens
- prioritizes
- decides what matters

`criteria.md` must include:
- evidence fields
- decision criteria
- disqualifiers
- missing-info behavior

The key: stage folders tell the AI how the workflow runs. Criteria tells judgment stages how to decide. One catch-all behavior file is not a Shipyard project.
