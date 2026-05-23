# Phase 4 Examples — Step by Step

## Step 1: Build criteria.md when judgment exists

_Coach reads reference.md "Criteria File Minimum" before this step._

Shipwright: "What evidence does the workflow need before any stage can make a judgment? Name the fields or signals."
User: "Time cost, frequency, repeated friction, and whether the problem blocks other work."
Shipwright: "Good — the workflow now knows what evidence to look for."

[Next turn]
Shipwright: "How should judgment stages choose? Name the criteria they use to decide."
User: "Choose the problem with the highest recurring time cost or coordination friction."
Shipwright: "Good — those criteria make the decision explicit."

[Next turn]
Shipwright: "When should a judgment stage NOT recommend, approve, or decide?"
User: "Do not recommend if the issue is rare, low-impact, or missing time/frequency evidence."
Shipwright: "Good — that keeps the workflow from forcing a bad answer."

[Next turn]
Shipwright: "What should a judgment stage do when the evidence is missing or weak?"
User: "Ask for a specific example and a rough time or frequency estimate."
Shipwright: "criteria.md is ready. Create criteria.md in your project folder. Put those four parts in it. Tell me when it's done."

---

## Step 2: Build one stage folder at a time

_Coach reads reference.md "Stage File Quality (ICM)" before reviewing._

**Stage: 01-intake**

Shipwright: "For intake, what does this stage receive?"
User: "A person opening the tool or describing their workflow."
Shipwright: "Good — that's the stage input."

[Next turn]
Shipwright: "For intake, what should this stage output for the next stage?"
User: "A structured workflow description with tasks, time costs, friction points, and tools mentioned."
Shipwright: "Good — that's the stage handoff."

[Next turn]
Shipwright: "For intake, what gate must be true before the next stage starts?"
User: "It has at least one repeated task and one friction or time-cost signal."
Shipwright: "Good — that's the stage gate."

[Next turn]
Shipwright: "Create 01-intake/context.md with Input, Routing, Output, and Gate. Tell me when it's done."
User: "Done."
Shipwright: "Paste 01-intake/context.md so I can verify it."
User: [pastes file]
Shipwright: "context.md is right — this stage has a routing map."

[Next turn]
Shipwright: "Create 01-intake/references.md. Put examples, criteria pointers, source material, or 'No extra references for this stage.' Tell me when it's done."
User: "Done."
Shipwright: "Paste 01-intake/references.md so I can verify it."
User: "No extra references for this stage."
Shipwright: "references.md is right — this stage has its support material."

**Stage rules — one instruction at a time:**

Shipwright: "Write one instruction for intake: opening question. Tell the AI exactly what to do."
User: "Ask about the workflow."
Shipwright: "That fails the one-stage test because 'ask about the workflow' could mean anything. What exact question should this stage ask first?"
User: "Ask the employee to describe their weekly workflow, repeated tasks, time drains, tools used, and places work gets stuck."
Shipwright: "That instruction works — it is stage-specific and names the evidence to collect."

[Next turn]
Shipwright: "Write one instruction for intake: handoff output."
User: "Summarize the workflow."
Shipwright: "That is too vague because the next stage needs specific fields. What exact fields should the intake stage output?"
User: "Output repeated tasks, time costs, waiting points, manual re-entry, repeated questions, tools mentioned, and missing evidence."
Shipwright: "That instruction works — it gives the next stage a concrete handoff."

[Next turn]
Shipwright: "Create 01-intake/rules.md with the verified stage instructions. Tell me when it's done."
User: "Done."
Shipwright: "Paste 01-intake/rules.md so I can verify every instruction made it in."
User: [pastes file]
Shipwright: "01-intake folder is complete — context.md routes it, references.md supports it, and rules.md runs only this stage."

---

## Step 3: Walk-through test

_Coach reads reference.md "Stage Handoff Test" before this step._

Shipwright: "Before we test with real input, let's walk through the workflow stage by stage. Someone opens your tool for the first time. Which stage starts, and what does it ask for?"
User: "01-intake starts and asks them to describe their workflow, repeated tasks, time drains, tools, and where work gets stuck."
Shipwright: "That handoff is covered. After 01-intake, what exact output goes to 02-diagnosis?"
User: "A list of repeated tasks, time costs, friction points, waiting points, and missing evidence."
Shipwright: "That handoff is covered. What is the most likely wrong thing the workflow could do?"
User: "It could diagnose a pain point without enough evidence."
Shipwright: "That is covered by criteria.md and the diagnosis gate. Walk-through complete — every stage handoff is covered."

---

## Step 4: Test in conversation

Shipwright: "I'll play the end-user and run each stage. You watch, then check whether each stage output gives the next stage what it needs.

[As end-user] 'I spend six hours every week combining updates from four supervisors and chasing missing updates.'

[01-intake output]
Repeated task: weekly report compilation. Time cost: six hours. Friction: inconsistent supervisor updates and chasing missing inputs.

[02-diagnosis output]
Pain point: weekly report compilation, because it has recurring time cost and coordination friction.

[03-response output]
Recommendation: one AI tool and three next steps.

Look at the run. For each stage — did its output give the next stage what it needed?"

User: "Yes. Intake gave diagnosis the evidence, diagnosis gave response the pain point, and response gave the final recommendation."
Shipwright: "Good — you tested the workflow and verified the stage handoffs. That's the skill."

---

## Gate pass

Shipwright: "Describe the staged workflow in one sentence."
User: "It collects workflow evidence, diagnoses the biggest pain point, then returns one AI recommendation with next steps."
Shipwright: "Is anything still blocking you from shipping this?"
User: "No."
Shipwright: "Then we're done building. Let's ship it."
[→ Phase 5]
