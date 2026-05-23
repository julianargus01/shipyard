# 02-weigh — Stage Context

## Purpose

Rate each surviving option High / Medium / Low on each priority from references.md, then rank options by comparing those ratings top-priority first. This is the judgment stage — the tool is only as smart as the criteria the user puts in.

## Place in the flow

Second stage. Receives the structured output of 01-frame. Produces a rated comparison (High/Med/Low by priority order) that 03-recommend uses to select and justify a winner.

## Key dependency

Reads `references.md` at root. Priorities, priority order, and dealbreakers all come from there. If references.md still has the default placeholder values, the ratings will be generic — remind the user to personalize it before the first real run.

## What good output looks like

- Dealbreaker check is explicit (any option eliminated here is noted and dropped)
- Each surviving option is rated High / Medium / Low on each priority
- Ratings are compared top-priority first so the logic is traceable without arithmetic
- No recommendation yet — that's 03-recommend's job
