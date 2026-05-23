# 02-design — Rules

## Input
The tagged inventory from 01-scan (table of files with type/topic/junk/dupe tags) plus the rules in context.md.

## Process
1. Read context.md: note the primary grouping strategy, naming convention, and depth preference.
2. Group the non-junk files by the primary grouping strategy (project / type / date as specified). Derive folder names from the `topic` tags for project-grouped files; use category names for type-grouped files.
3. Arrange folders into a hierarchy. Apply the depth rule from references.md (max 3-4 levels). Merge thin groups (fewer than 3 files) into a parent folder or an `misc/` catch-all rather than creating a near-empty folder.
4. Apply the naming convention from context.md to derive the cleaned filename pattern for each file type. Write the pattern as a template (e.g., `YYYY-MM_description-topic.ext`), not a per-file rename (03-plan does per-file renames).
5. Note any files whose correct home is ambiguous (could fit two folders). Mark them `AMBIGUOUS` with the two candidate paths.
6. Do not list junk/dupe files in the tree — they will be handled in 03-plan.

## Output
Two sections:

**A. Proposed folder tree** — ASCII tree showing every folder. Include a one-line rationale for each top-level folder.

Example:
```
projects/           ← one folder per client/project (from topic tags)
  acmecorp/
    invoices/
    contracts/
  personal/
    finances/
archive/            ← dated items with no active project
  2024/
misc/               ← items with topic: unknown and no obvious home
```

**B. Naming convention summary** — 3-5 bullet points stating the rules that will be applied in 03-plan (date format, case, separator, version suffix, etc.).

## Gate
Advance to 03-plan when: (a) every non-junk, non-dupe file from the inventory maps to exactly one folder in the tree, and (b) the naming convention is stated explicitly. If any file cannot be placed, resolve the ambiguity before advancing.
