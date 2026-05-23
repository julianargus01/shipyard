# 03-plan — Rules

## Input
Rated task table (High/Medium/Low per factor) and PROJECT list from 02-score.

## Process
1. Read `references.md` (root) for daily capacity limits and defer rules before bucketing.
2. Apply urgency overrides first: any task with Urgency=High and due within 48 hours enters the top-3 regardless of its Impact or Effort rating.
3. Fill remaining top-3 slots using priority order (NO math):
   a. Sort remaining tasks by Urgency (High first).
   b. Break ties by Impact (High first).
   c. Break remaining ties by Effort (Low effort first).
4. Check the top-3 against references.md capacity limit (no more than one High-effort item). If exceeded, note it — do not silently drop a task.
5. Place all non-top-3 tasks in "Do Later" unless they qualify for Defer.
6. Place Low-urgency, Low-impact tasks in "Defer" (or drop per references.md defer rules — note which and why).
7. List all PROJECT-flagged items in their own section unchanged.
8. If any top-3 item looks like a project (multi-step, not a single action), flag it with "(check: this may be a project)."

## Output
A four-section daily plan. Use the exact format below so it's readable at a glance.

Format:
```
## TODAY — Top 3
1. [Task] (Urgency: H | Effort: L/M/H | [capacity note if High effort])
2. [Task] (Urgency: H | Effort: L/M/H)
3. [Task] (Urgency: M | Impact: H | Effort: L)

## Do Later
- [Task] (Urgency: M | Impact: M)
...

## Defer
- [Task] (Urgency: L | Impact: L) — [reason: low urgency / low impact / no deadline]
...

## Projects Flagged
- PROJECT: [name]
...
```

## Gate
Exactly 3 items in Top 3 (or fewer only if the full task list has fewer than 3 items). Every task from 02-score appears in exactly one section (Top 3, Do Later, Defer, or Projects). No tasks invented. No numeric scores appear anywhere in the output. Capacity note present if top-3 contains more than one High-effort item. Each Defer entry has a reason.
