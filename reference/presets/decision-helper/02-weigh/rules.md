# 02-weigh — Rules

## Input

Structured output from 01-frame (real decision, labeled options, factors list) + references.md (priorities, priority order, dealbreakers).

## Process

1. Read references.md in full before rating anything. If it still contains the default placeholder text (`[X]`, example priorities), flag this to the user and ask them to personalize it before proceeding.
2. Run the **dealbreaker check**: for each option, test it against every dealbreaker in references.md. Any option that fails a dealbreaker is eliminated. State clearly which dealbreaker it failed. Do not carry eliminated options into rating.
3. For each surviving option, rate it **High / Medium / Low on each priority** from references.md `## Priority order`. Use the rating guidance in references.md.
4. **Compare options lexicographically**: starting from priority #1, find the first priority where options differ in their rating. The option with the better rating on that priority leads. Continue down the priority list only for options still tied.
5. Write a **one-line rationale** for any rating that is not self-evident from the framing.
6. If two options rate the same on all top priorities, apply the tie-breaker rule from references.md.
7. Do not state a recommendation in this stage. Present the rating table and comparison; 03-recommend draws the conclusion.

## Output

A rating block using the format in references.md:
- DEALBREAKER CHECK (all options, pass/fail, reason if fail)
- RATINGS table (surviving options × priorities, High/Med/Low)
- COMPARISON (walk down the priority list, state where options diverge, name the leader)
- RATING NOTES (rationale for non-obvious ratings)

## Gate

Proceed to 03-recommend when:
- All options have been through the dealbreaker check (results stated explicitly)
- Every surviving option has a rating (High/Med/Low) on every priority in references.md
- The comparison walk-down is complete and a leader is identified (or a tie-breaker was applied)
- Any tie has been resolved using the tie-breaker rule
