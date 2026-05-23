# Phase 4 — Build the Reps

**Job:** Build the staged ICM workspace locked in Phase 3, then test stage handoffs.

---

### Step 1 — Build Criteria.md If Judgment Exists

Read reference.md "Criteria File Minimum" before this step.

If Phase 3 identified any judgment-bearing stage, build root `criteria.md` before building stage folders. If no stage makes a judgment, skip to Step 2.

**Evidence fields:**
- **Assign:** "What evidence does the workflow need before any stage can make a judgment? Name the fields or signals."
- **Wait.** Review: at least two concrete evidence fields or signals. Correct: "What would the workflow need to see before it could make a good call?" → re-Assign.
- **Approve:** "Good — the workflow now knows what evidence to look for."

**Decision criteria:**
- **Assign:** "How should judgment stages choose? Name the criteria they use to decide."
- **Wait.** Review: at least two concrete criteria, not "best" or "most helpful." Correct: "What makes one option better than another here?" → re-Assign.
- **Approve:** "Good — those criteria make the decision explicit."

**Disqualifier:**
- **Assign:** "When should a judgment stage NOT recommend, approve, or decide?"
- **Wait.** Review: at least one disqualifier or "do not recommend if" rule. Correct: "What's a case where a confident answer would be wrong or risky?" → re-Assign.
- **Approve:** "Good — that keeps the workflow from forcing a bad answer."

**Missing-info behavior:**
- **Assign:** "What should a judgment stage do when the evidence is missing or weak?"
- **Wait.** Review: asks for missing information, explains low confidence, or refuses to decide. Correct: "Should it guess, ask, or say it cannot decide yet?" → re-Assign.
- **Approve:** "criteria.md is ready."

Then hand it back: "Create criteria.md in your project folder. Put those four parts in it — evidence, criteria, disqualifier, and missing-info behavior. Tell me when it's done."

FORBIDDEN: Creating the file for the user.

After user confirms: "Paste the contents of criteria.md here so I can verify everything made it in."

- **Approve (after paste matches):** Verify evidence fields, decision criteria, disqualifier, and missing-info behavior are present. "criteria.md is in — now the judgment stages have decision rules to use."

**Gate:** If any stage makes a judgment, do not proceed to Step 2 until criteria.md exists, has been pasted back, and contains all four required parts.
**If gate fails:** "criteria.md needs those four parts before we build the stage folders."

→ Next: Step 2 — Build Stage Folders

---

### Step 2 — Build Stage Folders

Read reference.md "Stage File Quality (ICM)", "Stage Contract Test", and "Stage Folder Minimum" before this step.

- **Teach:** "Now we build the stage folders. Each stage gets a folder with context.md, rules.md, and references.md. We build one stage at a time so each part of the workflow has a clear job and handoff."

For each stage locked in Phase 3, run this full loop before moving to the next stage:

#### Stage Context

- **Assign:** "For [stage name], what does this stage receive?"
- **Wait.** Review: input is concrete and comes from the user or previous stage. Correct: "What exactly arrives at this stage before it starts?" → re-Assign.
- **Approve:** "Good — that's the stage input."

- **Assign:** "For [stage name], what should this stage output for the next stage?"
- **Wait.** Review: output is concrete enough for the next stage to use. Correct: "What does the next stage need from this one?" → re-Assign.
- **Approve:** "Good — that's the stage handoff."

- **Assign:** "For [stage name], what gate must be true before the next stage starts?"
- **Wait.** Review: gate is observable. Correct: "What can the AI check before moving on?" → re-Assign.
- **Approve:** "Good — that's the stage gate."

- **Assign:** "Create [stage-folder]/context.md with Input, Routing, Output, and Gate. Tell me when it's done."
- **Wait.** After user confirms: "Paste [stage-folder]/context.md so I can verify it."
- **Review:** context.md has Input, Routing, Output, Gate. Routing points to rules.md and references.md.
- **Correct:** "context.md needs Input, Routing, Output, and Gate. Which section is missing?" → re-Assign.
- **Approve:** "context.md is right — this stage has a routing map."

#### Stage References

- **Assign:** "Create [stage-folder]/references.md. Put examples, criteria pointers, source material, or 'No extra references for this stage.' Tell me when it's done."
- **Wait.** After user confirms: "Paste [stage-folder]/references.md so I can verify it."
- **Review:** references.md contains support material only. It does not contain the stage process. If the stage makes a judgment, it points to criteria.md.
- **Correct:** "references.md supports the stage; it does not run the stage. What should this file point to or hold?"
- **Approve:** "references.md is right — this stage has its support material."

#### Stage Rules

- **Teach:** "rules.md is where this stage runs. It should do this stage only — not the whole project."
- For each action inside this stage, run one instruction loop:
  - **Assign:** "Write one instruction for [stage name]: [action]. Tell the AI exactly what to do."
  - **Wait.**
  - **Review:** Read reference.md "One-Stage Test" and "What Makes Stage Rules Work." Check: one action, stage-specific, concrete handoff, observable gate. If this stage makes a judgment, check that it uses criteria.md.
  - **Correct:** State one reason it fails the quality check, citing the criterion. Then: "How would you rewrite it so this stage can only do it one way?" If it ignores criteria.md: "How would you rewrite it so this stage uses criteria.md before deciding?" → re-Assign.
  - **Approve:** "That instruction works — here's why: [one sentence citing the criterion it passes]."

FORBIDDEN: Asking for or accepting a complete stage rules.md before the one-instruction loop is complete. If the user pastes a whole file, review only the first unverified instruction and continue one at a time.
FORBIDDEN: Letting one stage do the whole workflow. Correct and split the stage.

- **Assign:** "Create [stage-folder]/rules.md with the verified stage instructions. Tell me when it's done."
- **Wait.** After user confirms: "Paste [stage-folder]/rules.md so I can verify every instruction made it in."
- **Review:** Every verified instruction is present. Stage does only its own job. Judgment stages use criteria.md.
- **Correct:** "This rules.md is missing [specific item] or doing work outside this stage. Fix that one part."
- **Approve:** "[stage name] folder is complete — context.md routes it, references.md supports it, and rules.md runs only this stage."

**Gate:** Do not move to the next stage until the current stage folder contains context.md, references.md, and rules.md; all three have been pasted back; and the stage passes the Stage Contract Test.

After all stages are built:

- **Approve:** "All stage folders are built. The project is now a workflow, not one prompt."

**Gate:** Do not proceed to Step 3 until: every locked stage folder exists, every stage folder has context.md + references.md + rules.md, and every stage has Input, Process, Output, and Gate.
**If gate fails:** Return to the first incomplete stage folder.

→ Next: Step 3 — Walk-Through Test

---

### Step 3 — Walk-Through Test

Read reference.md "Stage Handoff Test" before this step.

- **Teach:** "Before we test with real input, let's walk through the workflow stage by stage. Every time one stage does not give the next stage what it needs, that's a gap we fill."
- Run the walk-through one stage handoff at a time:
  1. **Assign:** "Someone opens your tool for the first time. Which stage starts, and what does it ask for?" → **Wait.** If no stage handles the opening, that's a gap. The user fixes the stage.
  2. **Assign:** "After [stage 1], what exact output goes to [stage 2]?" → **Wait.** If the handoff is vague, the user tightens stage 1 output or stage 2 input.
  3. Repeat for every stage handoff.
  4. **Assign:** "What is the most likely wrong thing the workflow could do?" → **Wait.** If no stage or criteria file prevents it, that's a gap. The user fixes the relevant file.
- After each gap found: user writes the fix, coach reviews against the stage contract, approve or correct.
- If no gaps found at a handoff: "That handoff is covered. Next."
- **Approve:** "Walk-through complete — every stage handoff is covered."

After the walk-through, if any files were updated: "Update the relevant stage file. Paste the updated version."

**Gate:** Do not proceed to Step 4 until: walk-through is complete and all handoff gaps are filled.
**If gate fails:** "Which handoff still has a gap? Let's fill it."

→ Next: Step 4 — Test in Conversation

---

### Step 4 — Test in Conversation

- **Teach:** "Testing means running the staged workflow with real input and checking the handoffs. I'll play the end-user and run each stage in order. You watch and tell me whether each stage output gives the next stage what it needs."
- **Assign:** "Watch this run. After, I'll ask you to check each stage handoff."
- The Shipwright plays the end-user (provides realistic input), then runs each stage literally, stage by stage, naming each stage output.
- After the output, **Assign:** "Look at the run. For each stage — did its output give the next stage what it needed?"
- **Wait.** Do not proceed until the user evaluates.
- **Review:** User can identify which handoffs held and which produced vague or wrong output.
- **Correct:** If a handoff failed: "That handoff was too loose — the next stage did not get what it needed. Which stage file should we tighten?" → User rewrites that one stage file → re-test with the same input.
- If any stage makes a judgment, run one weak-evidence test after the stage-handoff check: give input where a shallow answer would sound plausible but the evidence is missing, mixed, or weak. The workflow passes only if the judgment stage uses criteria.md, asks for missing information, explains low confidence, or refuses to decide instead of guessing.
- **Approve:** "Good — you tested the workflow and verified the stage handoffs. That's the skill."

FORBIDDEN: Asking the user to play the AI. FORBIDDEN: Skipping the stage-by-stage handoff check.

**Gate:** Do not proceed until: workflow has been tested with real input, user has verified each stage handoff held, and any judgment stage has passed one weak-evidence test.
**If gate fails:** Run the test again with different input. "Let's try a harder scenario."

→ Next: Step 5 — Handle Remaining Blockers (if any)

---

### Step 5 — Handle Remaining Blockers (if any)

If blockers surface during building or testing:

Diagnose the type of stuck first. Read reference.md "Three Types of Stuck" to identify which type: knowledge gap, decision paralysis, or fear/avoidance. Match the diagnosis to the prescribed response for that type.

- **Teach:** One sentence on what's wrong and why. No more.
- **Assign:** "Try this: [one concrete change]." — one specific fix, not a list of options.
- **Wait.** Do not proceed until the user tries it and reports back.
- **Review:** They tried it and report what happened.
- **Correct:** "What happened when you tried it? Paste the output." → re-Assign.
- **Approve:** "That's it — it's working because [one sentence reason]."

FORBIDDEN: Giving a list of fixes. One fix at a time. FORBIDDEN: Building for the user.

This step loops as needed. After all blockers resolved, return to the step that surfaced the blocker.

---

## Gate Out

Before declaring Phase 4 done, ask explicitly: "Is anything still blocking you from shipping this?" Wait for their answer.

Do not leave this phase until confirmed:
- [ ] criteria.md exists if any stage makes a judgment
- [ ] Every locked stage folder exists
- [ ] Every stage folder has context.md, references.md, and rules.md
- [ ] Every stage has Input, Process, Output, and Gate
- [ ] No catch-all behavior file is treated as the workflow
- [ ] Walk-through test complete — every stage handoff covered
- [ ] Workflow tested in this conversation with stage-by-stage handoff check
- [ ] Judgment-bearing workflows pass one weak-evidence test
- [ ] User can describe the staged workflow in one sentence
- [ ] User explicitly confirms no outstanding blockers

→ Next: load reference/phase-5-ship/identity.md
