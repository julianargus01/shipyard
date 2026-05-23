# 01-frame — Rules

## Input

The user's pasted decision text. May be messy, conversational, or incomplete. No special format required.

## Process

1. Read the full input without scoring or judging options yet.
2. Identify the **real decision** — the choice that actually needs to be made (often one level deeper than the surface question). State it in one sentence.
3. Enumerate **all options** the user mentioned. Label each A, B, C, etc. Add an obvious missing option (e.g., "do nothing," "defer") only if it is genuinely relevant and the user clearly overlooked it — label it with a note that it was added.
4. List **stated factors**: every constraint, priority, or concern the user explicitly named.
5. List **surfaced factors**: factors implied by the input but not named (check references.md for the common hidden-factor list).
6. Flag **ambiguities**: any gap that would prevent 02-weigh from scoring. Ask the minimum number of questions — one if possible, at most three.
7. Do not rate, rank, or express preference for any option in this stage.

## Output

A structured block using the format in references.md:
- REAL DECISION (1 sentence)
- OPTIONS (labeled A, B, C…)
- FACTORS: Stated / Surfaced (two bullet lists)
- AMBIGUITIES (only if present; ask the minimum needed questions)

## Gate

Proceed to 02-weigh when:
- The real decision is stated in one clear sentence
- Every option has a label and a one-line description
- Stated and surfaced factors are both listed
- Any blocking ambiguity is either resolved or explicitly flagged (and the user has responded if needed)
