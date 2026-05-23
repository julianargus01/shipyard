# Brain-Dump Planner Reference

## Coach-facing build map

This is the preset map for Brain-Dump Planner. The Coach reads this privately before Phase 2 and Phase 3 so it knows what to teach, what input to request, and what routing table to add. Do not expose this map, this file name, or private stage names to the user.

| Build part | Preset value |
|---|---|
| User folder name | `brain-dump-planner` |
| User-facing files | `identity.md`, then `context.md` |
| Phase 3 input | A real pasted brain dump: tasks, worries, reminders, half-thoughts |
| Result preview | Clean task list, scores, top priorities, later/defer/project buckets |
| Confirmation rule | No external changes; user confirms the plan is usable |

### `context.md` fields

Teach these fields in order:

- `## Urgency`
- `## Effort`
- `## Impact`
- `## Scoring`
- `## Daily capacity`
- `## Defer rules`
- `## Urgency override`

The user's `context.md` is the second file they create in their own `brain-dump-planner` folder, after `identity.md`. Do not create a private root `context.md` here because it collides with the ICM-native `CONTEXT.md` on case-insensitive filesystems. Brain-Dump Planner uses `context.md` for user-facing judgment and this private `references.md` only as Coach support.

## Field guidance

### `## Urgency`
Teach the user to define what makes a task urgent in their world.

Default example:
- **High:** Has a hard deadline, is flagged important, others depend on it, or it is critical to a process
- **Medium:** Due within the week, or will create friction if delayed beyond today
- **Low:** No deadline pressure; can slip days without real consequence

### `## Effort`
Teach the user to calibrate effort to their actual energy, focus, and context-switching cost.

Default example:
- **Low:** 10–15 minutes, single action, no context-switching cost
- **Medium:** up to ~1 hour, or requires gathering info / switching context once
- **High:** several hours, multi-step, or needs deep focus / heavy coordination

### `## Impact`
Teach the user to define which outcomes matter most so the planner prioritizes their goals, not generic productivity.

Default example:
- **High:** Produces a completed deliverable, advances a key goal, or unblocks a project
- **Medium:** Useful but not critical; contributes incrementally
- **Low:** Nice-to-have, admin, or maintenance with no direct goal link

### `## Scoring`
Teach the user how urgency, impact, and effort combine into a ranked priority order (no math required).

Default example:
Rate each item High / Medium / Low on all three factors. Then rank by priority order:
1. Urgency override: any item due within 48 hours goes in today's top 3.
2. Sort by Urgency (High first).
3. Break ties by Impact (High first).
4. Break remaining ties by Effort (lower effort first).

### `## Daily capacity`
Teach the user to name what "a realistic day" means before ranking tasks.

Default example:
- Top-3 tasks: no more than one High-effort item (not three heavy tasks in the same day)
- "Do later" list: all remaining tasks that are not deferred
- Defer list: Low-urgency, Low-impact items, or anything with no clear owner/deadline

### `## Defer rules`
Teach the user the difference between keeping, dropping, and flagging items as projects.

Default example:
- Defer (keep, do another day): real task, score <= 1, or effort too high for today's capacity
- Drop (don't carry forward): vague thoughts with no action, duplicate items, "nice to know" with no follow-on
- Flag as project (not a task): anything that requires 3+ steps to complete; capture name only, don't score

### `## Urgency override`
Teach the user whether any hard-deadline item should force its way into today's top-3 regardless of where it falls in the priority order.

Default example:
If an item is Urgency=High and due within 48 hours, it enters the top-3 regardless of its Impact or Effort rating.

## Routing guidance

After the first passing run, the Coach returns to the user's `identity.md` and helps them add `## Routing`. For Brain-Dump Planner, the routing table should use plain step names like:

| Step | What happens |
|---|---|
| 1. Capture | Turn the messy brain dump into a clear list of tasks and project candidates. |
| 2. Score | Use `context.md` to rate each task by urgency, effort, and impact and rank by priority order. (Rules: `## Urgency`, `## Effort`, `## Impact`, `## Scoring`, `## Urgency override`) |
| 3. Plan | Turn the scores into a realistic daily plan with top tasks, later items, deferred items, and projects. (Rules: `## Daily capacity`, `## Defer rules`) |
| 4. Deliver | Present the finished plan to the user: top-3 for today, do-later list, defer list, and flagged projects. |
| 5. Confirm | Ask the user whether the plan is usable as-is. If anything feels off, adjust before closing. |
