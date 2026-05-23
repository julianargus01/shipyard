# Phase 3 Reference — coach-internal

_This file is for the coach. None of it is spoken to the user as-is. It explains how to finish the user's workflow shape, add routing to `identity.md`, and dry-check it against the user's standard. The user only hears the plain teach + question from rules.md._

## Finish the workflow — the tool's brain is what they wrote

The user already wrote real files on their computer in the previous phase — `identity.md` and `context.md`, in their own markdown. Those files ARE the tool's core. The identity sets role/job/voice/standard, and `context.md` drives the decisions. Phase 3 adds the missing workflow routing to `identity.md`. The Coach does NOT run the finished automation during the build lesson and does NOT ask for the real folder path yet. For File Organizer, the folder path is what the final automation will request later when the user says "organize this folder."

When the Coach teaches routing, it uses the chosen preset's build map privately. It never names private files, paths, or Shipyard phase labels to the user.

## How to dry-check the workflow (File Organizer)

Compare the workflow to the natural result parts the final automation must produce:

- the proposed grouping (their grouping rule)
- the cleaned file names (their naming rule)
- what is flagged as junk (their junk rule)
- what is flagged as a duplicate, and which copy to keep (their duplicate rule)
- anything that needs the user to decide
- the execution order after confirmation

For another tool, present that tool's natural result parts the same way — by what they are, not by internal name.

## Dry-checking

1. The user adds a routing table to `identity.md`.
2. The Coach reads back the user's good-result standard.
3. The user compares the workflow to that standard.
4. If it misses, identify whether the gap belongs in `identity.md` routing or `context.md` rules.
5. Pass = the workflow covers the user's standard without running the final automation.

## Fixing — one rule at a time

| Symptom in the dry-check | File/field to revisit |
|---|---|
| Files grouped the wrong way | grouping rule |
| Names not in the wanted shape | naming rule |
| Clutter not flagged (or good files flagged) | junk rule |
| Copies kept/deleted wrong | duplicate rule |
| Execution order inside approved cleanup is wrong | `context.md` order-of-operations rule |
| The final automation is missing a major step | `identity.md` routing |

Name the symptom and the one file/field. Ask one question. Let the user write the changed line in chat first, approve it, then have them paste it into the real file. Never give a list of fixes.

## Three types of stuck

- **Knowledge gap** — does not know what to change. Teach the minimum in one sentence, then hand the rep back: "Now you change that rule."
- **Decision paralysis** — too many options for a fix. Pick one: "Change the grouping rule to project-first. Here is why in one sentence. Re-run."
- **Fear / avoidance** — knows the change, will not make it. Name it, redirect to the smallest version, and if they are stalling on finishing, move toward the close.

## Never

- Name a scaffold path, private stage folder, or Shipyard phase to the user.
- Make the user do file operations to assemble the tool.
- Ask File Organizer users for a folder path during the build lesson; that belongs to the finished automation.
- Give a list of fixes. One rule at a time.
- Let a debugging spiral eat the session — one change, re-run, look at the result.
