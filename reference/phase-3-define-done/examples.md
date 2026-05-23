# Phase 3 Examples — Step by Step

## Step 1: Lock workflow stages

**Discovery — one at a time:**
Shipwright: "A Shipyard project is a workflow, not one prompt. Every project needs at least three stages: intake, work, and output. What starts the workflow — what does the user give it?"
User: "Their revenue and expenses for the month."

[Next turn]
Shipwright: "What stages does the AI go through, in order? Name at least three."
User: "First it reads the numbers, then it finds the biggest cash problem, then it explains what to fix."

[Next turn]
Shipwright: "What does the final stage give back to the user?"
User: "A clear explanation of where the cash is going and what to fix first."

**Correction — too vague:**
Shipwright: "The middle stage makes a judgment, so it needs criteria. What evidence should it use to choose the biggest cash problem?"
User: "The size of each expense, how often it happens, and whether it is larger than expected."

**Confirmation — one at a time:**
Shipwright: "Stage 1 is intake. Its job is to read the numbers and list the main revenue and expense facts. Correct?"
User: "Yes."

[Next turn]
Shipwright: "Stage 2 is diagnosis. Its job is to use criteria to identify the biggest cash problem. Correct?"
User: "Yes."

[Next turn]
Shipwright: "Stage 3 is response. Its job is to explain the diagnosis and one priority fix. Correct?"
User: "Yes."

**Application question:**
Shipwright: "Why does this need to be staged before we build anything?"
User: "Because then each part has a job and we can test whether one stage gives the next one what it needs."
Shipwright: "Workflow locked: intake → diagnosis → response. We build from these stages."

---

## Step 2: Write the definition of done — Part 1

Shipwright: "Done needs to be written down — not just in your head. Finish this sentence: 'This project is done when...'"
User: "Done when a small business owner can paste their numbers and get back a clear explanation of their cash flow problem."
Shipwright: "Good — that's the finish line."

---

## Step 2b: Write the success test — separate turn

Shipwright: "How will you know it worked? Name one real person or situation that proves it."
User: "When my friend who owns a bakery says she actually understands what to fix first."
Shipwright: "Written definition of done: 'Done when a small business owner can paste their numbers and get back a clear explanation of their cash flow problem.' Success test: 'When my friend who owns a bakery says she actually understands what to fix first.' We don't move either line."

---

## Step 4: Introduce the staged playbook

Shipwright: "Now we build the playbook — the folder that is your project. A Shipyard playbook has root files plus stage folders. Root files tell the AI where it is. Stage folders tell it how the workflow runs. In your own words: why does each stage need its own folder instead of one big instruction file?"
User: "Because each stage is doing a different part of the workflow."
Shipwright: "Exactly. Each stage gets its own folder because each stage has its own job, output, and gate."

---

## Step 4b: Introduce root files

Shipwright: "Two files live at the root. AGENTS.md tells the AI who it is. CONTEXT.md is the root routing map that points to the stage folders. The stages do the work. In your own words: what's the difference between AGENTS.md, CONTEXT.md, and a stage folder?"
User: "AGENTS.md is who it is, CONTEXT.md is the map, and stage folders are where the workflow happens."
Shipwright: "Right. Identity, map, workflow. We build AGENTS.md first."

---

## Step 5: Build AGENTS.md

Shipwright: "AGENTS.md always starts: 'You are [name or role].' How would you describe this AI starting with 'You are...'?"
User: "You are a cash flow advisor for small business owners."
Shipwright: "Good — that's the identity line."

[Next turn]
Shipwright: "Complete this: 'Your job is to...'"
User: "Your job is to help small business owners understand why their cash is tight and what to fix first."
Shipwright: "AGENTS.md is done: 'You are a cash flow advisor for small business owners. Your job is to help small business owners understand why their cash is tight and what to fix first.' That's the AI's brief. Create a file called AGENTS.md in your project folder. Put exactly that in it. Tell me when it's done."

User: "Done."
Shipwright: "Paste the contents of AGENTS.md here so I can verify it matches what we agreed on."
User: [pastes file]
Shipwright: "Matches what we agreed on. AGENTS.md gives the AI a consistent identity so it stays on task instead of drifting — that's why this file matters. Moving on."

---

## Step 6: Build CONTEXT.md with stage routing

Shipwright: "CONTEXT.md is the root routing map — not an instruction dump. It tells the AI what this project does and where the workflow stages live. In one sentence, what does this tool do?"
User: "It diagnoses cash flow problems for small business owners."
Shipwright: "Good — that's the opening line of CONTEXT.md."

[Next turn]
Shipwright: "Now the routing table. Root CONTEXT.md points to stage folders. Fill in the routing row for intake: Stage | Read this."
User: "intake | 01-intake/context.md"
Shipwright: "Good — that stage routes to its folder."

[Next turn]
Shipwright: "Fill in the routing row for diagnosis: Stage | Read this."
User: "diagnosis | 02-diagnosis/context.md"
Shipwright: "Good — that stage routes to its folder."

[Next turn]
Shipwright: "Fill in the routing row for response: Stage | Read this."
User: "response | 03-response/context.md"
Shipwright: "CONTEXT.md is done. It routes the project into stage folders instead of one big prompt. Create a file called CONTEXT.md in your project folder. Put exactly that in it. Tell me when it's done."

User: "Done."
Shipwright: "Paste the contents of CONTEXT.md here so I can verify the workflow routing table is right."
User: [pastes file]
Shipwright: "Routing table is right. The AI now knows the staged workflow and where each stage lives — that's a working playbook map. Moving on."

---

## Gate pass

Shipwright: "Let's check the gates. Workflow defined as at least three named stages?"
User: "Yes."
Shipwright: "Each stage has a distinct job and handoff?"
User: "Yes."
Shipwright: "AGENTS.md and CONTEXT.md exist as files — verified?"
User: "Yes."
Shipwright: "CONTEXT.md routes to stage folders, not one catch-all behavior file?"
User: "Yes."
Shipwright: "Good. Let's build the stage folders."
[→ Phase 4]
