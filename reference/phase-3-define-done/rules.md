# Phase 3 — Define Done

**Job:** Lock the smallest working version + binary success test + staged ICM workspace.

---

### Step 1 — Lock the Workflow Stages

Read reference.md "Workflow Model" and "Stage Contract" before this step.

- **Teach:** "A Shipyard project is a workflow, not one prompt. Every project needs at least three stages: intake, work, and output. Each stage gets its own folder because each stage has a different job."
- **Assign (discovery):** Ask these one at a time — one per turn:
  1. "What starts the workflow — what does the user give it?"
  2. "What stages does the AI go through, in order? Name at least three."
  3. "What does the final stage give back to the user?"
- **Wait** after each question. Do not proceed until they answer.
- **Assign (confirm — one at a time):** After discovery, lock each piece separately. One confirmation per turn:
  1. "So the input is [what they said]. Is that right?" → Wait.
  2. "Stage 1 is [stage name]. Its job is [job]. Correct?" → Wait.
  3. One more turn for each additional stage.
  4. "And the final output is [what they said]. Does that capture it?" → Wait.
  FORBIDDEN: Stacking multiple confirmations in one turn.
- **Review:** Workflow has at least three named stages, in order. Each stage has a distinct job. Each stage produces something the next stage can use. If any stage chooses, diagnoses, recommends, ranks, screens, prioritizes, or decides what matters, mark the workflow as judgment-bearing and require criteria.md.
- **Correct (too few stages):** "That's still one prompt, not a workflow. Break it into at least three stages: what happens first, what happens next, and what produces the final answer?"
- **Correct (vague stage):** "That stage is too vague because [reason]. What exactly does this stage receive, do, and pass forward?"
- **Correct (missing criteria):** "This stage makes a judgment. What criteria should it use, and what should it do when evidence is weak?"
- **Approve:** Before locking, one application question: "Why does this need to be staged before we build anything?" If they can demonstrate it ("each part has a job," "we can test handoffs," "not just a prompt"), confirm: "Workflow locked: [stage 1] → [stage 2] → [stage 3+]. We build from these stages." If vague, re-Teach: "A workflow works because each stage has a job, an output, and a gate. That's why it matters."

**Gate:** Do not proceed to Step 2 until: input is confirmed, at least three stages are named and confirmed, every stage has a distinct job, final output is confirmed, any judgment-bearing stage has criteria needs identified, and the user has answered the application question.
**If gate fails:** Re-confirm the missing element, split vague stages, or re-ask the application question.

→ Next: Step 2 — Write the Definition of Done

---

### Step 2 — Write the Definition of Done (Part 1: Done Sentence)

- **Teach:** "Done needs to be written down — not just in your head. A verbal finish line moves. A written one doesn't. We start with one sentence that says exactly when this project is complete."
- **Assign:** "Finish this sentence: 'This project is done when...'"
- **Wait.** Do not proceed until the user writes the sentence.
- **Review:** A specific minimum working state. Not "when it works well" or "when it's good."
- **Correct:** "What's the minimum it has to do? Describe the simplest version that counts as done." → re-Assign.
- **Approve:** "Good — that's the finish line."

**Gate:** Do not proceed to Step 2b until: user has written a specific done sentence.
**If gate fails:** "Picture someone using it for the first time. What do they do, and what do they get? That's your done sentence."

→ Next: Step 2b — Success Test

---

### Step 2b — Write the Definition of Done (Part 2: Success Test)

- **Teach:** "Now the proof. How will you know it actually worked — not 'I think it's good,' but a real signal you can point to?"
- **Assign:** "How will you know it worked? Name one real person or situation that proves it."
- **Wait.** Do not proceed until the user writes the sentence.
- **Review:** A specific, observable success signal — a real person, a real situation, a real reaction. Not "when people like it."
- **Correct:** "Who specifically would test this? What would they say or do that proves it worked?" → re-Assign.
- **Approve:** "Written definition of done: '[their exact done sentence].' Success test: '[their exact success sentence].' We don't move either line."

FORBIDDEN: Writing the definition of done for the user. FORBIDDEN: Combining, shortening, or rephrasing the user's sentences when confirming them. If their version is incomplete, Correct and re-Assign. Never draft it yourself.

**Gate:** Do not proceed to Step 3 until: user has written both sentences — the done sentence AND the success test.
**If gate fails:** Ask what specific outcome would prove it works to a stranger.

→ Next: Step 3 — Apply the Cutting Rule

---

### Step 3 — Apply the Cutting Rule

- **Teach:** "Before we build, we cut. For every feature or idea attached to this project, we ask: is this needed for the workflow to pass the definition of done, or is this extra? If it's extra, it goes to V2."
- **Assign:** "Looking at the stages we locked, is there anything attached to this project that isn't strictly necessary to pass the definition of done?"
- **Wait.**
- **Review:** They identify at least one thing to cut or confirm the staged workflow is already minimal.
- **Correct:** "What would happen if you removed [feature]? Would the staged workflow still pass the definition of done?"
- **Approve:** "Good — that's the minimum staged workflow. Everything else is V2."

**Gate:** Do not proceed to Step 4 until: scope is confirmed minimal against the staged workflow.
**If gate fails:** Walk through each feature against the definition of done.

→ Next: Step 4 — Introduce the Staged Playbook

---

### Step 4 — Introduce the Staged Playbook

Read reference.md "Required Root Structure" and "Stage Folder Structure" before this step.

Do not combine this step with Step 4b. One concept per turn.

- **Teach:** "Now we build the playbook — the folder that is your project. A Shipyard playbook has root files plus stage folders. Root files tell the AI where it is. Stage folders tell it how the workflow runs."
- **Assign:** "In your own words: why does each stage need its own folder instead of one big instruction file?"
- **Wait.**
- **Review:** They understand stage folders separate responsibilities and prevent one catch-all prompt.
- **Correct:** "A prompt tries to do everything at once. A workflow separates the job into stages so each part can be tested. Why does that matter for your project?"
- **Approve:** "Exactly. Each stage gets its own folder because each stage has its own job, output, and gate."

FORBIDDEN: Approving a one-file behavior build. FORBIDDEN: Saying a catch-all instruction file is enough.

**Gate:** Do not proceed until: user can explain why stage folders matter.
**If gate fails:** Re-Teach with: "One folder per stage keeps the AI from blending intake, work, and output into one vague prompt."

→ Next: Step 4b — Introduce Root Files

---

### Step 4b — Introduce Root Files

Do not combine this step with Step 4. One concept per turn.

- **Teach:** "Two files live at the root. AGENTS.md tells the AI who it is. CONTEXT.md is the root routing map that points to the stage folders. The stages do the work."
- **Assign:** "In your own words: what's the difference between AGENTS.md, CONTEXT.md, and a stage folder?"
- **Wait.**
- **Review:** They understand AGENTS.md = identity, CONTEXT.md = root routing, stage folders = workflow work.
- **Correct:** "AGENTS.md is who the AI is. CONTEXT.md is the map. Stage folders are where each part of the workflow happens. Which is which?"
- **Approve:** "Right. Identity, map, workflow. We build AGENTS.md first."

**Gate:** Do not proceed to Step 5 until: user can distinguish root files from stage folders.
**If gate fails:** Give a concrete analogy — "AGENTS.md is the employee's name tag. CONTEXT.md is the building directory. Stage folders are the rooms where the work happens."

→ Next: Step 5 — Build AGENTS.md

---

### Step 5 — Build AGENTS.md

Read reference.md "AGENTS.md Template" before reviewing the user's work in this step.

Follow the file creation protocol. One field at a time. Never call this file a "system prompt," "brain," or any other term — it is AGENTS.md.

**Field 1 — Identity line:**
- **Teach:** "AGENTS.md always starts the same way: 'You are [name or role].' This gives the AI a consistent identity so it doesn't drift."
- **Assign:** "How would you describe this AI in one sentence — starting with 'You are...'?"
- **Wait.**
- **Review:** Starts with "You are" + a specific role (not generic).
- **Correct:** "Make the role more specific. Instead of 'an assistant,' what kind of assistant? For who?"
- **Approve:** "Good — that's the identity line."

**Gate:** Do not proceed to Field 2 until: identity line confirmed.

**Field 2 — Job line:**
- **Teach:** "'Your job is to...' — one sentence that describes exactly what the AI does for the user. This is what it does, not who it is."
- **Assign:** "Complete this: 'Your job is to...'"
- **Wait.**
- **Review:** One concrete job. Not a list. Not vague.
- **Correct:** "What's the single most important thing it does? Cut everything else."
- **Approve:** "AGENTS.md is done: '[full content].' That's the AI's brief."

**Gate:** Do not proceed until: both fields confirmed.

Then hand it back: "Create a file called AGENTS.md in your project folder. Put exactly that in it. Tell me when it's done."

FORBIDDEN: Do not create the file for the user. The user creates it.

After user confirms file exists: "Paste the contents of AGENTS.md here so I can verify it matches what we agreed on." Do not proceed until they paste it and it matches.

- **Approve (after paste matches):** "Matches what we agreed on. AGENTS.md gives the AI a consistent identity so it stays on task instead of drifting — that's why this file matters. Moving on."

**Gate:** Do not proceed to Step 6 until: user confirms AGENTS.md exists AND has pasted the contents for verification AND approval has been given with reason.
**If gate fails:** "The file needs to exist in your project folder before we move on. Create AGENTS.md now, then paste what's in it."

After approving AGENTS.md, the only allowed next step is Step 6 — Build CONTEXT.md. Do not load Phase 4.

→ Next: Step 6 — Build CONTEXT.md

---

### Step 6 — Build CONTEXT.md

Read reference.md "CONTEXT.md Is Always a Routing Map" and "Example Root CONTEXT.md" before reviewing the user's work in this step.

Follow the file creation protocol. One field at a time.

**Field 1 — What this project does:**
- **Teach:** "CONTEXT.md is the root routing map — not an instruction dump. It tells the AI what this project does and where the workflow stages live. The first section is one sentence: what does this tool do?"
- **Assign:** "In one sentence, what does this tool do?"
- **Wait.**
- **Review:** One clear sentence. Could stand alone as a description.
- **Correct:** "If someone read only that sentence, would they know exactly what the tool does?"
- **Approve:** "Good — that's the opening line of CONTEXT.md."

**Gate:** Do not proceed to Field 2 until: opening line confirmed.

**Field 2 — Workflow routing table:**
- **Teach:** "Now the routing table. Root CONTEXT.md points to stage folders. Each row is one workflow stage and the context.md inside that stage folder. The format is: Stage | Read this."
- For each locked stage, ask one row at a time:
  - **Assign:** "Fill in the routing row for [stage name]: Stage | Read this."
  - **Wait.**
  - **Review:** Row names the stage and points to `[stage-folder]/context.md`.
  - **Correct:** "The Read this cell should point to the context.md inside that stage folder. What is the folder path for this stage?"
  - **Approve:** "Good — that stage routes to its folder."
- **Review after all rows:** At least three stage rows. Rows match the locked workflow order. No row points to one catch-all behavior file.
- **Correct (catch-all file):** "That points to one file, not a staged workflow. Root CONTEXT.md must route to the stage folders. What's the first stage folder?"
- **Approve:** "CONTEXT.md is done. It routes the project into stage folders instead of one big prompt."

Then hand it back: "Create a file called CONTEXT.md in your project folder. Put exactly that in it. Tell me when it's done."

FORBIDDEN: Do not create the file for the user.

After user confirms file exists: "Paste the contents of CONTEXT.md here so I can verify the workflow routing table is right." Do not proceed until they paste it and it matches.

- **Approve (after paste matches):** "Routing table is right. The AI now knows the staged workflow and where each stage lives — that's a working playbook map. Moving on."

**Gate:** Do not proceed until: user confirms CONTEXT.md exists AND has pasted the contents for verification AND approval has been given with reason AND CONTEXT.md routes to at least three stage folders in workflow order.
**If gate fails:** "The file needs to exist before we move on, and it needs stage-folder routing. Create CONTEXT.md now, then paste what's in it."

→ Next: Step 7 — Confirm Test Plan

---

### Step 7 — Confirm Test Plan

- **Teach:** "Before we start building, one more thing: we test the workflow here in this conversation. I'll run the stages in order so you can watch the handoffs: one stage output must give the next stage what it needs."
- **Assign:** "Does that make sense — we test the stage handoffs right here?"
- **Wait.** Do not proceed until the user responds.
- **Review:** User confirms they understand testing happens in this conversation and includes stage handoffs.
- **Correct:** "When we test, I run each stage and check whether its output feeds the next stage. You watch and tell me if the handoff works. Clear?"
- **Approve:** "Good. Testing plan locked: right here, stage by stage."

**Gate:** Do not proceed until: user confirms testing will happen in this conversation and includes stage handoffs.
**If gate fails:** "We need to agree on how we test before we build. Testing happens here — I run the stage workflow. You watch. Okay?"

---

## Gate Out

Do not declare Phase 3 done until every box is checked aloud with the user:
- [ ] AGENTS.md and CONTEXT.md exist as actual files in the workspace (verified by paste)
- [ ] Workflow defined as at least three named stages, in order
- [ ] Each stage has a distinct job and handoff
- [ ] Judgment-bearing stages have criteria needs identified
- [ ] Definition of done written (not just verbal)
- [ ] CONTEXT.md routes to at least three stage folders using Stage | Read this
- [ ] No catch-all behavior file is treated as the project workflow
- [ ] Testing plan confirmed: "We'll test stage handoffs here in this conversation"

→ Next: load reference/phase-4-build/identity.md
