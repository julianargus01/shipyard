# File Organizer Reference

## Coach-facing build map

This is the preset map for File Organizer. The Coach reads this privately before Phase 2 and Phase 3 so it knows what to teach, what input to request, and what routing table to add. Do not expose this map, this file name, or private stage names to the user.

| Build part | Preset value |
|---|---|
| User folder name | `file-organizer` |
| User-facing files | `identity.md`, then `context.md` |
| Phase 3 build task | Add workflow routing to `identity.md`; do not ask for a folder path during the build lesson |
| Final automation input | User says "organize this folder" and provides a folder path |
| Final automation output | Cleanup preview, approved file changes, and final folder path for review |
| Confirmation rule | The final automation never moves, renames, or deletes until the user approves the preview |

### `context.md` fields

Teach these fields in order:

- `## How to group`
- `## Naming`
- `## Junk`
- `## Duplicates`
- `## Order of operations`

The user's `context.md` is the second file they create in their own `file-organizer` folder. Do not create a private root `context.md` here because it collides with the ICM-native `CONTEXT.md` on case-insensitive filesystems.

### Routing guidance

In Phase 3, the Coach helps the user add `## Routing` to `identity.md`. For File Organizer, the routing table should use plain step names like:

| Step | What happens |
|---|---|
| 1. Request folder | User says "organize this folder" and provides the folder path. |
| 2. Audit | Inspect the folder and identify file types, topics, junk, and duplicates. (Rules: `## Junk`, `## Duplicates`) |
| 3. Plan | Use `context.md` to propose folders, cleaned names, review items, and exact changes. (Rules: `## How to group`, `## Naming`) |
| 4. Ask approval | Show the preview and wait for the user to approve. |
| 5. Organize | Apply only the approved moves and renames; junk and duplicates are separated for review, never deleted. (Rule: `## Order of operations`) |
| 6. Share review path | Give the final folder path so the user can review the organized result. |
