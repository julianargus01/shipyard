# File Organizer — Routing Context

## Entry point
User provides a messy folder path. A raw file/folder listing is fallback only when live file access is not available.

## Stage flow
```
[folder path]
      ↓
  01-scan        classify every item → tagged inventory
      ↓
  02-design      propose folder tree + naming convention  ← reads the user's context.md
      ↓
  03-plan        concrete move/rename/delete preview + flags + execution order
      ↓
  confirm        user approves the preview before any file changes happen
      ↓
  execute        move/rename/delete only the approved actions
```

## Key dependency
Every stage reads the user's `context.md`. The judgment encoded there (grouping logic, naming convention, junk/duplicate rules) governs all decisions, especially in 02-design.

## Stage files
Each stage folder contains:
- `context.md` — what the stage handles and its place in the flow
- `references.md` — support material and examples
- `rules.md` — Input / Process / Output / Gate

## How to run
1. Receive the folder path and audit the folder when live file access is available. If not, ask for a pasted listing as fallback.
2. Execute 01-scan to produce the tagged inventory. Do not expose the internal stage name to the user.
3. Execute 02-design using the inventory + the user's `context.md`.
4. Execute 03-plan using the design output + the user's `context.md`.
5. Deliver the final preview and ask for explicit confirmation.
6. After confirmation, execute only the approved move/rename/delete actions when live file access is available. If access is not available, say so plainly and leave the user with the runnable preview.
