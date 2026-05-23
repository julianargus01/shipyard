# Decision Reference

## Coach-facing build map

This is the preset map for Decision Helper. The Coach reads this privately before Phase 2 and Phase 3 so it knows what to teach, what input to request, and what routing table to add. Do not expose this map, this file name, or private stage names to the user.

| Build part | Preset value |
|---|---|
| User folder name | `decision-helper` |
| User-facing files | `identity.md`, then `context.md` |
| Phase 3 input | A real pasted decision with options and any known constraints |
| Result preview | Framed decision, rated options compared by priority order, winning recommendation with rationale, named runner-up, and the flip condition (the one change that would reverse the call) |
| Confirmation rule | User confirms the recommendation is usable as-is; if a constraint was missed, loop back to framing — no external tool or folder needed |

### `context.md` fields

Teach these fields in order:

1. **Decision priorities** — the 3-5 things the tool should optimize for when
   comparing options, ranked from most important to least important.
2. **Priority order** — the ranked order of priorities (most important first) so
   the Weigh step compares options lexicographically, top priority first.
3. **Dealbreakers** — hard stops that eliminate an option before rating.
4. **Tie-breaker** — the qualitative rule to use when two options rate the same on the top priorities.

The private sections below are the source of truth for those four fields. They support the user's `context.md`; they are not a third user-facing file.

<!-- << PERSONALIZE: This file is the heart of the tool. Edit all four sections. >>
The priority order and dealbreakers here are what make recommendations yours, not generic.
Spend 5-10 minutes on this. The more honest you are, the better the output.
-->

## Priorities (what matters most, in order)

<!-- << PERSONALIZE: Replace the examples below with your real priorities. Order = rank.
Be specific — vague values produce vague ratings. 3-5 items is ideal. >> -->

<!-- List your top 3-5 priorities. Order = rank. Be specific — vague values produce vague ratings.
Examples (replace with yours):
1. Preserves optionality — keeps future doors open
2. Low ongoing time cost — I can't add another high-maintenance thing
3. Financial risk stays bounded — capped downside I can absorb
4. Aligns with where I want to be in 2 years
5. Can start within 2 weeks with what I already have
-->

1. Preserves optionality — keeps future doors open
2. Low ongoing time cost — I can't add another high-maintenance thing
3. Financial risk stays bounded — capped downside I can absorb
4. Aligns with where I want to be in 2 years
5. Can start within 2 weeks with what I already have

## Priority order

<!-- << PERSONALIZE: List your priorities from most important (#1) to least important (last).
This ranked order — not numeric weights — is how 02-weigh compares options.
The tool checks the highest-ranked priority first; lower priorities only matter when options tie above. >> -->

<!-- Rank your priorities most-important to least-important.
02-weigh will rate each option High / Medium / Low on each priority,
then pick the option that does best starting from priority #1 down.
-->

1. Preserves optionality
2. Low ongoing time cost
3. Financial risk bounded
4. 2-year alignment
5. Fast to start

## Dealbreakers

<!-- << PERSONALIZE: Replace the examples with your real hard stops. Be honest —
a dealbreaker you wouldn't actually enforce is just noise. 2-4 items is typical. >> -->

<!-- Hard stops. If an option fails any of these, it is eliminated before rating.
Examples (replace with yours):
- Requires more than $X committed upfront
- Requires quitting or pausing current work
- Outcome is irreversible within 90 days
-->

- Requires more than $[X] committed upfront with no exit
- Requires quitting or pausing current primary work
- Outcome is fully irreversible within 90 days

## Tie-breaker

<!-- When two options rate the same (High/Med/Low) on all top priorities, what breaks the tie? -->

<!-- << PERSONALIZE >> -->
Prefer the option that is easier to undo or exit.

## Routing guidance

After the first passing run, the Coach returns to the user's `identity.md` and helps them add `## Routing`. For Decision Helper, the routing table should use plain step names like:

| Step | What happens |
|---|---|
| 1. Receive input | User pastes the decision: options, known constraints, and any context. |
| 2. Frame | Restate the real decision and the full option set; flag anything ambiguous and resolve it before proceeding. |
| 3. Align | Confirm the framing is right — ask one question if the scope or options are still unclear; only proceed when the user agrees the frame is correct. |
| 4. Weigh | Apply dealbreakers to eliminate disqualified options, then rate survivors High / Medium / Low on each priority from `context.md`; compare by priority order (top priority first); apply tie-breaker if options rate the same on the top priorities. (Rules: `## Dealbreakers`, `## Priorities`, `## Priority order`, `## Tie-breaker`) |
| 5. Recommend | State the winning option first, explain in words why it does best on the highest-ranked priorities, name the runner-up, and state the flip condition — the one change that would reverse the recommendation. (Rules: `## Priorities`, `## Priority order`) |
| 6. Confirm | Ask the user whether the recommendation is usable as-is or whether a constraint was missed; if a gap is found, loop back to step 3. |
