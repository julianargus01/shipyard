# 01-scan — Rules

## Input
A folder path provided by the user when live file access is available. If live file access is not available, use a raw file/folder listing pasted by the user as fallback. A pasted listing may include full paths, indented tree format, or a flat list of filenames.

## Process
1. If given a folder path, audit the folder and list its files/folders without changing anything. If given a pasted listing, parse it line by line and identify folders vs. files (folders end with `/` or have sub-items).
2. For each file: assign a `type` tag using the categories in `references.md`.
3. For each file: extract a `topic` tag if the filename contains a project name, client name, proper noun, or date-anchored identifier. If none, tag as `topic: unknown`.
4. Flag `junk-candidate: yes` for any file matching the junk patterns in `context.md`.
5. Flag `duplicate-candidate: yes` for any filename that appears more than once in the listing (same name, same extension, different path).
6. Do not rename, move, or propose structure yet.

## Output
A tagged inventory table. Format:

```
| # | Filename | Type | Topic | Junk? | Dupe? | Notes |
|---|----------|------|-------|-------|-------|-------|
| 1 | report_final.docx | document | unknown | no | no | — |
| 2 | Copy of report_final.docx | document | unknown | yes | yes | junk pattern + dupe |
...
```

Follow with a one-paragraph summary: total files, breakdown by type, count of junk/dupe candidates.

## Gate
Advance to 02-design when every file in the audited folder or fallback listing has a row in the inventory. If the folder path cannot be accessed, ask for permission or ask the user to paste the listing as fallback. If the listing is empty or unreadable, stop and ask the user to re-paste.
