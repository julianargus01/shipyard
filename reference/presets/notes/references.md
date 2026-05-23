# Notes Cleaner — Judgment Reference

## Coach-facing build map

This is the preset map for Notes Cleaner. The Coach reads this privately before Phase 2 and Phase 3 so it knows what to teach, what input to request, and what routing table to add. Do not expose this map, this file name, or private stage names to the user.

| Build part | Preset value |
|---|---|
| User folder name | `notes` |
| User-facing files | `identity.md`, then `context.md` |
| Phase 3 input | Real pasted messy notes from a meeting, call, lecture, brainstorm, or transcript |
| Result preview | Summary, decisions, action items, open questions, optional follow-up draft |
| Confirmation rule | User reads the recap and confirms it is usable; offer one round of targeted fixes if anything is off. No file saves or external actions required. |

### `context.md` fields

Teach these fields in order:

1. **Task vs. note rule** — what counts as a real action item versus a note,
   key point, decision, open question, or noise.
2. **Vague-task rule** — what makes an action item too unclear to act on, and
   which missing details should be flagged.
3. **Grouping rule** — how key points should be grouped, deduplicated, or left
   flat in the final recap.
4. **Recap format** — which sections the cleaned notes should include, in what
   order, and when to include a follow-up message draft.

The private sections below are the source of truth for those four fields. They
support the user's `context.md`; they are not a third user-facing file.

<!-- << PERSONALIZE: This file is the core of your tool. Edit sections 1-4. ~10-15 min. >> -->

## 1. Action vs. note rule

<!-- << PERSONALIZE: What makes something a task vs. an observation?
Default rule below. Adjust to match how you think. >> -->

A statement is a **task** if:
- Someone needs to do something specific, OR
- A follow-up is needed to make something happen.

A statement is a **note/key point** if:
- It records what was said, decided, or observed — no follow-up required to complete.

**Edge cases — treat as tasks:**
- Implied actions ("we should look into X" = task, owner TBD)
- Commitments stated in passing ("I'll send that over" = task)

## 2. Vague-task flag

<!-- << PERSONALIZE: What makes a task too vague to act on?
Default: flag if missing BOTH owner AND date. Adjust the threshold here. >> -->

Flag a task as **VAGUE** if it is missing:
- [ ] A clear action (what exactly to do), OR
- [ ] An owner (who), AND no context to infer one

A task missing a date is **not** automatically vague — undated tasks are acceptable.

**VAGUE label format:** append `[VAGUE — missing: <what's missing>]` inline.

## 3. Grouping rules

<!-- << PERSONALIZE: How should key points be grouped?
Default: by topic/theme. Alternatives: by speaker, by project, chronologically. >> -->

Group key points by **topic or theme**.
If fewer than 4 key points exist, no grouping needed — list flat.
Identical or near-identical points: keep one, mark `(duplicate removed)`.

## 4. Recap format

<!-- << PERSONALIZE: Adjust section names, order, and detail level.
Remove sections you never need. Add sections you always want (e.g. "Parking Lot"). >> -->

Default recap structure:
1. **Summary** — 2-4 sentences, what this was and what mattered
2. **Decisions** — numbered list, past-tense declarative
3. **Action Items** — table: `| Task | Owner | Due | Notes |`
4. **Open Questions** — bulleted, unanswered items needing a future response

Optional section (include when follow-up is needed):
5. **Follow-up Message Draft** — brief, send-ready message summarizing next steps

## 5. Fixed rules (do not change — these are system invariants that govern all outputs regardless of your other settings)

- Do not invent owners or dates not present or strongly implied in the notes.
- Do not merge distinct decisions into one.
- Do not drop open questions — they are output, not noise.

## Routing guidance

After the first passing run, the Coach returns to the user's `identity.md` and helps them add `## Routing`. For Notes Cleaner, the routing table should use plain step names like:

| Step | What happens |
|---|---|
| 1. Receive notes | User pastes raw notes (meeting, call, lecture, brainstorm, or transcript) into the conversation. |
| 2. Extract | Read the raw notes and label each item: task, decision, key point, open question, or noise. (Rule: `Action vs. note rule`) |
| 3. Organize | Use `context.md` to flag vague tasks, group key points by topic, deduplicate, and preserve decisions and open questions. (Rules: `Vague-task flag`, `Grouping rules`) |
| 4. Format | Turn the organized notes into the final recap structure and voice defined in `context.md`. (Rule: `Recap format`) |
| 5. Deliver recap | Present the finished recap to the user in full. |
| 6. Confirm | Ask the user to confirm the recap is usable; offer one round of targeted fixes if anything is off. |
