# 03-recommend — Rules

## Input

Rating output from 02-weigh (dealbreaker results, ratings table, priority-order comparison, rating notes).

## Process

1. Identify the **winner**: the option that came out ahead in 02-weigh's priority-order comparison. If a tie-breaker was applied in 02-weigh, honor it.
2. State the **recommendation** in one sentence, leading with the option name. No preamble.
3. Write **2–4 reasoning bullets**, each grounded in a specific priority from references.md and the rating it received. Explain in words why the winner does best on the highest-ranked priorities — no point totals, no numeric gaps.
4. Name the **runner-up** (the option that led on the next priority after the winner was established) and write one sentence: the specific condition under which it would be the better choice.
5. Write **"what would flip this"**: one or two concrete, testable conditions that would reverse the recommendation. Must be specific (name the priority, the rating that would change, the option it would elevate).
6. State a **confidence level** (High / Medium / Low) with one sentence of justification. Base it on how many top priorities the winner leads on and the presence of any unresolved ambiguities from 01-frame.
7. Follow the voice in identity.md: direct, no hedging, no softening language. See references.md for "no hedging" guidance.

## Output

A recommendation block using the format in references.md:
- RECOMMENDATION (1 sentence)
- WHY (2-4 bullets, each naming a priority and the rating that drove the call — no point totals)
- RUNNER-UP + flip condition (2 sentences max)
- WHAT WOULD FLIP THIS (1-2 conditions, specific — name the priority and rating that would change)
- CONFIDENCE (level + 1-sentence justification)

## Gate

Output is complete when:
- A recommendation is stated (not implied)
- Every WHY bullet names a priority from references.md and references the rating (High/Med/Low)
- Runner-up is identified (or "none" if only one option survived)
- At least one flip condition is stated and is concrete
- Confidence level is assigned with a reason
