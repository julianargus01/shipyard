# 03-plan — References

## Move/rename line format
Each action line follows this pattern:
```
[ACTION] "old-name.ext"  →  destination/path/new-name.ext
```
Actions: MOVE, RENAME, MOVE+RENAME, DELETE, REVIEW (user must decide).

## Confirmation rule
The action list is a preview first. Do not execute MOVE, RENAME, MOVE+RENAME, or DELETE until the user explicitly confirms the preview. REVIEW items are never executed automatically.

## Example action lines
```
MOVE+RENAME  "Invoice March copy.pdf"  →  projects/acmecorp/invoices/2024-03_invoice-acmecorp.pdf
MOVE         "contract_v3.docx"        →  projects/acmecorp/contracts/contract_v3.docx
DELETE       "Copy of Invoice March.pdf"  →  (duplicate of above; delete)
DELETE       ".DS_Store"               →  (system junk)
REVIEW       "notes.txt"               →  ambiguous: could be projects/acmecorp/ or misc/; user decides
```

## Order-of-operations heuristic
When executing after confirmation, use the order in the user's `context.md`. If no custom order is given, use this safe default:
1. Separate junk and duplicates first.
2. Move or rename files with an obvious destination.
3. Leave ambiguous files as REVIEW items; never move them automatically.

## Closing summary format
End the plan with:
- Total files: N
- To move/rename: N
- To delete: N (junk) + N (duplicates)
- Needs review: N
- Estimated execution time: ~X min after confirmation
- Confirmation prompt: "Check this preview. If it looks right, say `confirm`, and I will make only these changes."
