# 02-weigh — References

## Rating guidance

**Scale:** High / Medium / Low per criterion per option — no numbers, no arithmetic.
- **High** = this option clearly satisfies this priority
- **Medium** = partial fit; this priority is met with notable gaps or conditions
- **Low** = this option does not satisfy this priority

**Comparison method (lexicographic, no math):**
Work through priorities in order from `## Priority order` in references.md.
1. Find the highest-ranked priority where options differ in their rating.
2. The option with the better rating on that priority wins.
3. If options tie on all top priorities, apply the tie-breaker from references.md.

No sums, no multiplication, no point totals.

## Rating table format

```
DEALBREAKER CHECK:
  Option A: [pass/fail — note which dealbreaker if fail]
  Option B: [pass/fail]
  ...

RATINGS (surviving options only):
| Priority (ranked)       | Option A | Option B | Option C |
|-------------------------|----------|----------|----------|
| 1. [Priority 1]         |  High    |  Medium  |  High    |
| 2. [Priority 2]         |  Medium  |  High    |  Low     |
| 3. [Priority 3]         |  High    |  Low     |  Medium  |
| 4. [Priority 4]         |  Low     |  High    |  Medium  |
| 5. [Priority 5]         |  High    |  High    |  Low     |

COMPARISON:
  Priority 1: A=High, B=Medium, C=High → B eliminated from lead; A and C tied — check priority 2.
  Priority 2: A=Medium, C=Low → A leads.
  Winner: A (does best starting from the top priority down)

RATING NOTES:
  [Brief rationale for any rating that isn't obvious — 1 line per notable rating]
```

## Common rating mistakes to avoid

- Don't conflate "I like this option" with "this option rates well on these criteria" — rate against criteria only
- If you can't rate an option on a criterion because the framing is ambiguous, note it explicitly rather than guessing
- When options tie on the top priorities, use the tie-breaker in references.md — do not invent a numeric total
