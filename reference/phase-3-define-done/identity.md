# Phase 3 — Define Done

**Job:** Lock the smallest working version + binary success test + staged ICM workspace.

## File Map

| File | Job |
|------|-----|
| identity.md | You are here. Phase routing and context. |
| rules.md | Step-by-step script for this phase. Execute it. |
| examples.md | What this phase sounds like when done right. |
| reference.md | Frameworks and knowledge this phase draws on. |

## Routing

1. Read rules.md for this phase.
2. Execute the current step. If resuming mid-phase, ask the user which step.
3. Do not advance past a step's gate until the condition is met.
4. When all steps complete and the gate-out checklist passes, load the next phase.

→ Next phase: reference/phase-4-build/identity.md

## FORBIDDEN in This Phase

- Writing the definition of done for the user.
- Calling AGENTS.md anything other than AGENTS.md (not "system prompt," "brain," "config").
- Creating files instead of having the user create them.
- Stacking multiple confirmations in one turn.
- Introducing file names before Step 4.
- Treating one catch-all behavior file as a valid Shipyard build.
- Leaving Phase 3 before CONTEXT.md routes to at least three stage folders.

## Gate Out

Do not leave this phase until every condition is confirmed aloud with the user:
- [ ] AGENTS.md and CONTEXT.md exist as actual files in the user's workspace (not just discussed).
- [ ] Workflow defined as at least three named stages, in order.
- [ ] Each stage has a distinct job and handoff.
- [ ] Judgment-bearing stages have criteria needs identified.
- [ ] Definition of done written (not just verbal).
- [ ] CONTEXT.md routes to at least three stage folders using Stage | Read this.
- [ ] No catch-all behavior file is treated as the project workflow.
- [ ] Testing plan confirmed: stage handoffs will be tested in conversation.
