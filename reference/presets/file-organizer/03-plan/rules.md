# 03-plan — Rules

## Input
The proposed folder tree + naming convention from 02-design, and the tagged inventory from 01-scan (including junk/dupe flags).

## Process
1. For each non-junk, non-dupe file in the inventory: write one action line using the format in references.md. Derive the destination path from the 02-design tree and apply the naming convention. Action is MOVE if the name is already clean, MOVE+RENAME if the name needs fixing, RENAME alone if it stays in-place.
2. For each file flagged `junk-candidate: yes` in 01-scan: write a DELETE line with the junk reason in parentheses.
3. For each file flagged `duplicate-candidate: yes`: write a DELETE line for the copy to remove; write a MOVE or MOVE+RENAME line for the keeper (the one in the most relevant folder per context.md).
4. For each file marked AMBIGUOUS in 02-design: write a REVIEW line with both candidate paths stated.
5. Sort executable action lines using the order-of-operations rule from the user's `context.md`. If no custom order exists, use the safe default in references.md: deletions for junk/duplicates first, clear moves/renames second, review items last.
6. Group the output into sections: Deletions, Moves and renames, Needs review.
7. Write the closing summary (counts + estimated time) using the format in references.md.

## Output
A complete action preview with sections. This preview is not permission to execute; the user must approve it first.

```
## Deletions
DELETE  "Copy of Invoice March.pdf"  →  (duplicate)
DELETE  ".DS_Store"                  →  (system junk)
...

## Moves and renames
MOVE+RENAME  ...
...

## Needs your review
REVIEW  "notes.txt"  →  projects/acmecorp/ OR misc/  (you decide)
...

---
Total: 42 files | Move/rename: 30 | Delete: 8 (3 junk, 5 dupes) | Review: 4
Estimated execution time: ~1 min after confirmation
```

## Gate
The preview is complete when every file from the 01-scan inventory appears exactly once across all sections (Deletions, Moves and renames, or Needs review). Verify the count matches before delivering. After delivering the preview, ask for explicit confirmation before any move, rename, or delete action is executed.
