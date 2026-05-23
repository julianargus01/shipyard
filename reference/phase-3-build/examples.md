# Phase 3 Examples — Build the Workflow

_Worked thread: the same user's **File Organizer**. The user has already written two real files on their computer — `identity.md` and `context.md` — in their own markdown. Now the coach helps the user add the workflow routing to `identity.md`, then dry-checks it against the user's standard. The coach does not ask for a real folder path and does not run the finished automation during this build lesson._

---

## D. Workflow vs. Rules

Coach: "You have the tool's identity and its decision rules. One thing is still missing: the workflow. The workflow is the order the finished agent follows when someone uses it. Your `context.md` rules still matter — especially `Order of operations` — but those rules live inside the workflow."

Coach: "In your own words: what is the difference between the workflow and the rules?"

User: "The workflow is the steps it follows. The rules are how it decides inside those steps."

Coach: "Right. The workflow is the path. The rules are the judgment it uses along the path."

---

## D2. Add Routing

_Beat A — Teach the routing table first_

Coach: "The workflow goes into `identity.md` as a markdown table called `## Routing`. A markdown table organizes information in rows and columns — each `|` starts a new column, and the line of dashes under the top row marks the header. Here is what a tiny one looks like:

```markdown
| Step | What happens |
|---|---|
| 1. Look | you check what is in the folder |
```

That is the whole pattern — a header row, a divider row, then one row per step. You will build yours one row at a time as we name each step."

_Beat B — Build the table row-by-row_

Coach: "Someone hands this tool a messy folder. What is the first thing it should do?"

User: "Look at what is in the folder?"

Coach: "Right — it audits the folder before touching anything. That is step one. Does that step make a decision, or is it just a handoff?"

User: "It's making a decision — it is figuring out what is junk and what is not."

Coach: "Exactly. The Audit step uses the Junk and Duplicates rules from your `context.md`. Add that as row one in your `## Routing` table: `| 2. Audit | you scan the folder; you flag items using the Junk and Duplicates rules |`. What comes next?"

User: "It figures out a plan?"

Coach: "Good. It proposes a cleanup plan. That step makes decisions about grouping and naming — which rules from your `context.md` does it draw on?"

User: "How to group and Naming?"

Coach: "Yes. Add that as the next row: `| 3. Plan | you propose folders and names using How to group and Naming; you mark junk and duplicates |`. And before it moves anything?"

User: "The user has to approve it."

Coach: "Exactly — that is a handoff, not a decision. Add it: `| 4. Approve | the user reviews and approves |`. Then what?"

User: "It organizes the stuff that was approved."

Coach: "Yes — and that step has a rule too. Which one?"

User: "Order of operations."

Coach: "Right. Add that row: `| 5. Organize | you execute only approved changes, following Order of operations |`. One more step after that?"

User: "Gives back the folder so you can check it?"

Coach: "Right — it hands back the final folder path to review. That is a handoff. Add it: `| 6. Hand off | you give the final folder path for review |`. And before all of those steps there is a first one — the tool has to receive the folder. Add that at the top: `| 1. Receive | user provides the folder |`."

_Beat C — Read back the complete table and confirm_

Coach: "Here is the complete routing table we built:

```markdown
## Routing
| Step | What happens |
|---|---|
| 1. Receive | user provides the folder |
| 2. Audit | you scan the folder; you flag items using the Junk and Duplicates rules |
| 3. Plan | you propose folders and names using How to group and Naming; you mark junk and duplicates |
| 4. Approve | the user reviews and approves |
| 5. Organize | you execute only approved changes, following Order of operations |
| 6. Hand off | you give the final folder path for review |
```

Receive, Approve, and Hand off do not use a rule — they are handoff points, not decisions. Three steps draw on rules; three do not. Does that look complete?"

User: "Yes."

Coach: "That is well-formed — now `identity.md` says not only who the tool is and how it runs, but which rules it draws on at each step."

Coach: "Paste those lines at the bottom of `identity.md`. Save it. Tell me when it is done."

User: "done"

Coach: "Your two files now work together. `identity.md` holds the path and names the rules at each step. `context.md` holds the rules themselves. The tool knows who it is, how it decides, and how each step connects to the right judgment."

---

## E. Dry-Check

Coach: "Before we run it, do a quick paper check. Look at the workflow you wrote and your good-result standard."

Coach: "Check the workflow against your good-result standard: files grouped by topic, plain folder names, not too many top-level folders, junk and duplicates separated before anything moves, and a clear preview. Does this workflow cover what has to happen?"

User: "Yes. It audits, plans, asks approval, separates junk and duplicates first, then organizes."

Coach: "That passes the dry-check. Now we run it."

---

## F. Run It

_Beat F1 — Load the tool_

Coach: "Now I will run the tool you built. Let me read your files first."

_(Coach reads `identity.md` and `context.md` from the user's `file-organizer` folder.)_

Coach: "Reading your tool from your `file-organizer` folder — got it. I have your steps and your rules."

_Beat F2 — Get the target folder_

Coach: "Now, which folder do you want to organize? Give me the path or drag it in."

User: "~/Documents/ProjectStuff"

_Beat F3 — Audit_

Coach: "Here is what I see in that folder: 47 files, no subfolders. Groups I can see: budget spreadsheets (6), meeting notes (11), design exports labeled 'final', 'final2', 'final_REAL' (9), random screenshots (8), a few files with names like 'asdf.docx' or 'untitled3.pdf' that give no clue what they are (5), and leftover ZIP archives that look like duplicates of already-extracted folders (8)."

_Beat F4 — Show the plan and get approval_

Coach: "Here is the proposed cleanup:

Folders to create and what moves in:
- `budget/` — the 6 spreadsheets
- `meeting-notes/` — the 11 notes files
- `design-exports/` — the 9 design files, renamed to drop the 'final'/'final2'/'REAL' suffixes

Junk and duplicates — separated into a `_review/` subfolder, not deleted:
- The 8 ZIP archives (likely duplicates of extracted folders)
- The 8 screenshots with no clear project connection

Left in place for you to review:
- The 5 unclear files ('asdf.docx', 'untitled3.pdf', etc.) — I cannot tell what project they belong to

Does this plan look right to you? Say yes to continue, or tell me what to change."

User: "Yes, looks good."

_Beat F5 — Organize_

Coach: "Done. Junk and duplicates moved to `_review/` first, then files sorted into their folders, unclear files left in place. Here is your organized folder: `~/Documents/ProjectStuff`. Take a look."

---

## G. Fix-Only Loop

Coach: "Does the result meet your good-result standard? If something is broken or wrong, tell me what."

User: "The design files still have 'export' in the name — I wanted plain names like 'homepage.png', not 'homepage-export.png'."

Coach: "That is a naming rule, not a workflow step. It belongs in `context.md`. What one line would you add or change there?"

User: "'Remove the word export from file names when cleaning up design files.'"

Coach: "Add that line under your naming rules in `context.md`. Save it. Tell me when it is done."

User: "Done."

Coach: "Running it again on the same folder."

_(Re-run. Design file names now clean.)_

---

_Tweak-deflect beat_

User: "While we are at it, could we also sort files by date and add a date prefix to each name?"

Coach: "That is a later improvement. Right now we get it working and meeting your standard. Does the current result meet your standard?"

User: "Yes."

---

## H. Close

Coach: "That runs clean. The tool works on your real folder. Two files on your computer, written by you: `identity.md` holds who the tool is and how it runs. `context.md` holds how it decides. You wrote both, the workflow ran, and the result meets your standard."

---

## Alternate run — a pasted-text tool (Brain-Dump Planner)

_This excerpt shows only the parts that differ from the File Organizer run above: Sections F and G. Sections D, E, and H follow the same pattern; only the input type changes._

---

## F. Run It

_Beat F1 — Load the tool_

Coach: "Now I will run the tool you built. Let me read your files first."

_(Coach reads `identity.md` and `context.md` from the user's `brain-dump-planner` folder.)_

Coach: "Got your files from your `brain-dump-planner` folder. I have your steps and your rules."

_Beat F2 — Get the input_

Coach: "Paste your brain dump here — everything you are juggling right now. Do not worry about order or format."

User:
```
Call dentist
Finish the slide deck for Tuesday — really important
Reply to Marcus about the contract
grocery run
Cancel gym membership been meaning to do this forever
research new CRM options maybe
Fix the broken login on the staging site — blocking the whole team
Read that long article on pricing strategy
Pick up dry cleaning
Write Q2 goals for my 1:1 next week
```

_Beat F3 — Run the tool and present the result_

_(Coach captures tasks, scores each one using the user's urgency / effort / impact rules and scoring formula, applies daily capacity and defer rules, then presents the plan.)_

Coach: "Here is your plan.

**Top tasks for today** (do these first)

| Task | Score | Note |
|---|---|---|
| Fix the broken login on staging | 5 | Urgency override — hard deadline, blocking the team |
| Finish the slide deck for Tuesday | 4 | High urgency, high impact |
| Write Q2 goals for next week's 1:1 | 3 | Due soon, medium effort |

**Do later** (score ≥ 2, not urgent today)

- Reply to Marcus about the contract
- Call dentist

**Defer** (real task, score ≤ 1, or effort too high for today)

- Research new CRM options
- Read pricing strategy article

**Drop** (no clear action)

- Grocery run (no detail — add specifics if you want to track it)
- Pick up dry cleaning (same)

**Flagged as project** (three or more steps — capture the name, do not score)

- Cancel gym membership (requires finding the policy, contacting them, and confirming — flag as a project)"

---

## G. Fix-Only Loop

Coach: "Does that plan meet your good-result standard? If something is broken or wrong, tell me what."

User: "The dentist call is pretty urgent — I need to do it today. It scored too low."

Coach: "That is a scoring issue. Your urgency rule may not cover short calls with same-day need. What one line would you add or change in `context.md` under `## Urgency`?"

User: "'A call or email that has to happen today counts as Urgency 3 even when there is no hard external deadline.'"

Coach: "Add that line under `## Urgency` in `context.md`. Save it. Tell me when it is done."

User: "Done."

Coach: "Running the plan again on the same dump."

_(Re-run. Dentist call scores Urgency 3. It enters the top tasks for today alongside the slide deck; Q2 goals move to do-later.)_

---

_Tweak-deflect beat_

User: "Can we also add a time estimate to each task?"

Coach: "That is a later improvement. Right now we get it working and meeting your standard. Does the current plan meet your standard?"

User: "Yes."
