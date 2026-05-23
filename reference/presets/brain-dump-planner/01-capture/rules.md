# 01-capture — Rules

## Input
A raw pasted text block from the user. May include tasks, worries, half-formed ideas, reminders, and noise in any order or format.

## Process
1. Read the entire dump once before extracting anything.
2. Identify every distinct action or potential task — including those buried mid-sentence.
3. Split any compound items (multiple actions joined by "and" / "then" / "also") into separate tasks.
4. Rewrite each task to start with a clear verb (Send / Review / Call / Write / Decide / Schedule / Fix / etc.).
5. Flag any item requiring 3+ steps as PROJECT — write "PROJECT: [name]" and do not expand it.
6. Drop: vague thoughts with no action, filler phrases, exact duplicates. If in doubt, keep.
7. Number every output item sequentially starting at 1.

## Output
A numbered list of atomic tasks plus any PROJECT flags. No scores, no categories — just clean items.

Format:
```
1. [Verb] [object/detail]
2. [Verb] [object/detail]
...
PROJECT: [name]
```

## Gate
Every item starts with a verb (or is labeled PROJECT). No item contains "and" joining two distinct actions. List is free of vague thoughts and duplicates. Count of output items is fewer than or equal to count of raw inputs (some split, some dropped — never invented).
