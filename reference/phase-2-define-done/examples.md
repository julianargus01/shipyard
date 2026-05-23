# Phase 2 Examples — Build the Core Files (hands-on)

_Worked thread: a user building a **File Organizer** — a tool that takes a messy folder, previews the exact changes, then organizes it after confirmation. The user ends with real files on their computer, written in markdown, by their own hand. The rhythm is always: teach one field → user answers → user writes that field in proper markdown in the chat → Coach approves the chat markdown → user copies those exact lines into the real file inside `file-organizer` → save → next field. The Coach checks the chat content, not the desktop file._

---

## Step 0 — Make the folder, explain the first file, create it, and learn markdown

### Step 0a — Make the folder

Coach: "Before we build anything, your tool needs a home — one real folder on your computer. Everything your tool is will live as a few small files inside it. The folder is the tool. No app, no code — just files the AI reads."

Coach: "First step: make a folder on your desktop. Call it `file-organizer`. Then let me know when you're done."

User: "Done — I made a folder called file-organizer on my desktop."

Coach: "That is the home for your tool. What just happened — you now have one real place where the whole tool lives."

### Step 0b — Explain the first file (identity.md)

Coach: "You're going to write two files. The first is `identity.md` — the file that says who your tool is. It holds five things: who the agent is, the tool's job, its voice, what a good result looks like, and what to avoid. We'll do them one at a time, starting with who the agent is. We will write each piece in plain text — I will show you how in just a moment. In a moment, I will walk you through making that file."

User: "Got it."

### Step 0c — Create the first file (identity.md)

Coach: "Create a markdown file inside your `file-organizer` folder. If you are using TextEdit, choose Format → Make Plain Text first. If it saves as `identity.txt`, rename it in Finder to exactly `identity.md`. Not `identity.md.txt`, not `identity.md.rtf`, and not `identity.rtf`. Leave it open. Tell me when it is ready."

User: "Ready."

Coach: "Good. Now let me show you how to write it."

### Step 0d — Teach markdown plainly

Coach: "The file you just made is written in markdown. Markdown is just plain text the AI reads. There are only three things you need: a `#` at the start of a line makes a heading. A `-` at the start of a line makes a list item. Everything else is plain text — you just type it.

```markdown
# My Tool
- first rule
- second rule
```

The `#` line is a heading. The two `-` lines are a list. That is the whole of it. Each time we write a piece of your tool, you will write the markdown here first. I will check it. Then you will put those same lines into the text file in your folder."

Coach: "Quick check: when you write your file, which line gets the `#`, and which lines get the `-`?"

User: "The title line gets the `#`, and each rule gets a `-`."

Coach: "That is markdown. What just happened — you now know enough to write every file in this tool. Headings, lists, plain text."

---

## File 1 — identity.md

### Role

Coach: "The first line tells the AI who it is acting as. Keep it simple. This is the role the tool steps into every time it runs."

Coach: "In one short line: who is this agent? Hint — for this tool, something like 'You are a file organization assistant.'"

User: "You are a file organization assistant."

Coach: "That is who the agent is."

Coach: "Now write just that role field in markdown here in the chat. Use this shape:

```markdown
# Identity

## Role
[who the agent is]
```"

User:

```markdown
# Identity

## Role
You are a file organization assistant.
```

Coach: "That is well-formed — heading, role field, and who the agent is. Now paste those same lines into `identity.md` inside your `file-organizer` folder. Save it. Tell me when it is done."

User: "Done."

Coach: "What just happened — the file now tells the AI who it is."

### Job

Coach: "This file talks directly to the agent, so the line should say `you`, not `it`. In one sentence: what do you do? Hint — say what goes in and what happens after confirmation, like 'You take my messy folder, show me the changes first, then organize it after I confirm.'"

User: "You take my messy folder, show me what you will move or rename, then turn it into a clean folder after I approve it."

Coach: "That is the job line — written to the agent."

Coach: "Now write just that job field in markdown here in the chat. Use this shape:

```markdown
# Identity

## What you do
[your job sentence]
```"

User:

```markdown
## What you do
You take my messy folder, show me what you will move or rename, then turn it into a clean folder after I approve it.
```

Coach: "That is well-formed — field name and your job line. Now paste those lines under the role section in `identity.md`. Save it. Tell me when it is done."

User: "Done."

Coach: "What just happened — the first piece of your tool is now in the real file."

### Voice

Coach: "Next: the voice. The voice is how your TOOL sounds when it hands you back a result — plain, blunt, warm, technical. Pick how YOUR tool should sound, so it sounds like you. This is not about how you talk about the tool to other people, and it is not my voice — it is your tool's."

Coach: "How should your tool sound when it gives you the result? Hint — pick the closest in your own words: 'short and direct, no filler,' 'warm and plain,' or 'precise and technical.' Then give me one line your tool might actually say."

User: "Short and direct. A line it would say: 'Preview ready. Three files will move, two are junk.'"

Coach: "That is the voice your tool will use on every run."

Coach: "Now write just the voice field in markdown here in the chat."

User:

```markdown
## Voice
Short and direct. "Preview ready. Three files will move, two are junk."
```

Coach: "That is well-formed — the voice is in markdown, and the sample line shows how it sounds. Now paste those lines under the job section in `identity.md`. Save it. Tell me when it is done."

### Good Result

Coach: "One more thing goes in this file: what a good result looks like. A tool that does not know what 'good' means hands you something plausible but useless. You set the bar."

Coach: "When this tool gives you back a result, what makes you say 'yes, that is exactly right'? Hint — be concrete, like 'every file ends up in a folder I would have picked, named the same way, and I approved the changes first.'"

User: "Everything grouped by the client it belongs to, the names all match, and nothing moves until I approve the preview."

Coach: "That is your bar for a good result — a finish line the tool can be measured against."

Coach: "Now write that good-result field in markdown here in the chat."

User:

```markdown
## A good result
Everything is grouped by the client it belongs to, the names all match, and nothing moves until I approve the preview.
```

Coach: "That is well-formed — one heading, one checkable standard. Now paste those lines under the voice section in `identity.md`. Save it. Tell me when it is done."

### Avoid

Coach: "And the opposite: what should it never do? Naming the bad result keeps the tool from drifting into something that looks fine but is wrong."

Coach: "What would make a result wrong for you — something you would reject on sight? Hint — the opposite of what good looks like."

User: "Burying everything five folders deep, or renaming files so I cannot tell what they are."

Coach: "That is the line the tool will not cross."

Coach: "Now write that avoid field in markdown here in the chat."

User:

```markdown
## Avoid
Burying everything five folders deep, or renaming files so I cannot tell what they are.
```

Coach: "That is well-formed — one heading, one clear line the tool will not cross. Now paste those lines under the good-result section in `identity.md`. Save it. Tell me when it is done."

User: "Done."

Coach: "That is your first real file, on your computer. What just happened — your tool now has an identity you wrote: who it is, what it does, how it talks, what good looks like, and what it avoids. Next we write the second file: the rules it uses to decide."

---

Coach: "The second file holds your tool's rules — how it decides. A tool that organizes anything has to make calls, and without your rules it guesses. We will write the rules so it decides the way you would. One at a time, in markdown, into a real file."

Coach: "Create a second markdown file inside your `file-organizer` folder. If you are using TextEdit, choose Format → Make Plain Text first. If it saves as `context.txt`, rename it in Finder to exactly `context.md`. Not `context.md.txt`, not `context.md.rtf`, and not `context.rtf`. Leave it open. Tell me when it is ready."

User: "Ready."

### Grouping

Coach: "First rule: how should it group your files? Hint — by project, by type, or by date."

User: "By project — I think in terms of the client."

Coach: "That is your grouping rule."

Coach: "Now write that grouping rule in markdown here in the chat."

User:

```markdown
# context

## How to group
By project — I think in terms of the client.
```

Coach: "That is well-formed — file heading, rule heading, and your grouping rule. Now paste those same lines into `context.md`. Save it. Tell me when it is done."

### Naming

Coach: "Next: how should files be named? Hint — the shape, like 'client, then what it is, then date, lowercase with dashes.'"

User: "Client, then what it is, then date — like acme-invoice-2024-03."

Coach: "That is your naming rule."

Coach: "Now write that naming rule in markdown here in the chat."

User:

```markdown
## Naming
Client, then what it is, then date — like acme-invoice-2024-03.
```

Coach: "That is well-formed — the pattern and an example are both there. Now paste those lines under the grouping rule in `context.md`. Save it. Tell me when it is done."

### Remaining Rules

Continue the same loop for:

- `## Junk`
- `## Duplicates`
- `## Order of operations`

Each rule is answered by the user, written in markdown in the chat, approved by the Coach, then copied into `context.md` before the next rule begins.

Coach: "That is your second real file, on your computer. What just happened — your tool now has its judgment in your words: it will decide files the way you decide them."
