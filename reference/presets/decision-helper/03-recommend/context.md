# 03-recommend — Stage Context

## Purpose

Turn the rating table and priority-order comparison into a clear, usable recommendation — with reasoning, the runner-up, and the condition that would flip the call.

## Place in the flow

Final stage. Receives the scoring output of 02-weigh. Produces a recommendation the user can act on immediately.

## What good output looks like

- Recommendation is stated first, in one sentence, without hedging
- Reasoning explains why the winner won in terms of the user's own criteria — not generic logic
- Runner-up is named with one sentence on what would make it the better choice instead
- "What would flip this" is specific and actionable — a real condition, not a vague "it depends"
- Total length: short enough to read in 60 seconds
