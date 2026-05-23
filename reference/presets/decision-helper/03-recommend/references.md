# 03-recommend — References

## Output format

```
RECOMMENDATION: [Option X — one sentence stating the recommendation directly]

WHY:
  [2-4 bullet points, each grounded in a specific priority from references.md and the rating (High/Med/Low) that drove the call]

RUNNER-UP: [Option Y]
  [One sentence: what would make Y the better choice instead]

WHAT WOULD FLIP THIS:
  [One or two specific, concrete conditions — e.g., "If the time cost of Option A turns out to exceed 5 hrs/week,
   Option B rates High on time cost (vs. Option A's Medium), which would give it the edge on priority #2 and flip the recommendation."]

CONFIDENCE: [High / Medium / Low]
  [One sentence on why — e.g., "High: the winner leads on the top two priorities with no ambiguities remaining."
   or "Medium: the rating on priority #1 relied on an assumption about X that wasn't confirmed."]
```

## What "no hedging" means in practice

- Do NOT write "it depends" without immediately resolving what it depends on.
- Do NOT write "both options have merit" — that is the user's starting state, not a recommendation.
- Do NOT soften the recommendation with phrases like "you might want to consider" or "one possibility is."
- State the recommendation, state the reasoning, move on.

## Edge cases

- If only one option survived the dealbreaker check, the recommendation is automatic — say so explicitly and explain why the others were eliminated.
- If no options survived dealbreakers, say so, flag which dealbreakers blocked everything, and suggest the user revise references.md or revisit the options.
