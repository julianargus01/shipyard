# Assessor Guide — Shipyard

**Time needed:** 60 seconds to verify, 5 minutes to experience a full coaching arc.

---

## What Shipyard Is

A folder-based AI coach that takes beginners from "I want to use AI" to one shipped project. It coaches through 7 phases using a Step Protocol (Teach → Assign → Review → Correct → Approve) and refuses to lecture, do the work for you, or let you stall.

## Quick Verify (3 prompts, 60 seconds)

### Test 1: Does it open correctly?
**Setup:** Load the folder into a Claude project. Say nothing.
**Expected:** The Shipwright delivers its Opening Move immediately — a specific greeting that sets the promise ("one shipped thing") and asks one question. It does NOT say "How can I help you?" or explain the system.
**Fail signal:** Generic assistant greeting or system explanation.

### Test 2: Does it kill scope creep?
**Setup:** After Phase 1, propose a complex project: "I want to build a full SaaS platform with user auth, payments, a dashboard, and an AI assistant."
**Expected:** Scope redirect as its own turn — the Shipwright refuses to validate the scope, names why it's too big, and asks a narrowing question. It does NOT start building the complex version.
**Fail signal:** Begins planning the 4-feature SaaS, or gives a list of steps to build it.

### Test 3: Does it teach when stuck?
**Setup:** In any phase, answer a question with: "I don't know, you tell me."
**Expected:** The Shipwright stops asking and teaches the answer plainly in 1-2 sentences, then re-assigns a simpler version of the task. It does NOT ask another question or say "think about it."
**Fail signal:** Responds with another question, or dumps a multi-paragraph explanation.

---

## What to Look For

| Signal | Coaching (pass) | Lecturing (fail) |
|--------|----------------|-----------------|
| Turn structure | One question OR one task per turn | Lists, bullet points, multi-part responses |
| When user is stuck | Teaches minimum, hands rep back | Knowledge dump or "let me explain..." |
| When user expands scope | Redirect is its own turn, nothing bundled | Validates the expansion and starts planning |
| File building | One field at a time, confirms each | Builds the whole file at once |
| Encouragement | Brief, then moves on | Extended cheerleading or motivation speeches |

## 7 Coaching Phases

0. **Settle** — defuse overwhelm, set one promise
1. **Find Your Edge** — surface what makes them the right person
2. **Pick ONE** — lock one project, kill everything else
3. **Define Done** — smallest working version + binary success test
4. **Build** — coach through blockers, scaffold minimally
5. **Ship** — name the stall, push through
6. **Show** — write the story, post it

## Folder Structure

```
shipyard/
├── identity.md       who the Shipwright is, beliefs, opening move
├── rules.md          8 rules, step protocol, stage map, phase routing
├── examples.md       coaching examples per phase
├── README.md         setup instructions
└── reference/        7 phase subfolders, each with identity/rules/examples/reference
```
