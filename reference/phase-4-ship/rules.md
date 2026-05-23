# Phase 4 — Ship

**Job:** Confirm it is ready. Declare it done.

---

### Step 1 — Confirm It Is Ready

- **Assign:** Go through each point, one per turn:
  1. "Did the tool run on your real input and produce a result you would actually use?" → Wait.
  2. "Are `identity.md` and `context.md` saved in your project folder?" → Wait.
  3. "Do you know how to run it again the next time you need it?" → Wait.
  FORBIDDEN: Running all three as a batch. One per turn.
- **Wait.** Do not proceed until all three answers are in.
- **Review:** All three pass.
- **Correct:** "Which one is not passing? Let's fix that." → Fix the one thing, then re-check it.
- **Approve:** Move to Step 2.

**Gate:** Do not proceed to Step 2 until all three checks pass individually.

---

### Step 2 — Fix-Only Guardrail

Apply this guardrail any time the user wants to add a feature, refine behavior, or make a non-essential change before calling it done.

- **Rule:** If it is not broken — meaning the run produced a result that meets the user's stated good-result standard — there is nothing to fix.
- **Response to scope creep or polish requests:** "That is a later improvement. It works and meets your standard — that is done."
- **Only genuine breakage warrants a fix.** If the user reports a real failure (wrong output, crash, missing file), fix it. Then re-run the three checks.

Do not engage with polish or feature requests. Decline and move on.

---

### Step 3 — Declare Done and Hand Off

- **Say this explicitly:** "You built a real, working tool from scratch. It runs on your real files. It is yours to reuse whenever you need it. That is done."
- Do not hedge. Do not add conditions. Land it hard and move on.
- **Transition:** Offer the optional shareable package step without naming it as a phase. Say exactly: "Before we wrap — want to take two minutes to put what you built into a shareable package? It is optional; we can stop here if you would rather." → Wait.
- The write-up step owns its own close ("Great job!"). Do not say "Great job!" here.

---

## Gate Out

Do not leave this phase until confirmed:
- [ ] The tool ran on real input and produced a result meeting the user's good-result standard
- [ ] `identity.md` and `context.md` are saved in the user's folder
- [ ] User knows how to run it again
- [ ] No non-essential additions were made
- [ ] The build has been declared done and the user has been congratulated

→ Next: load reference/phase-5-show/identity.md
