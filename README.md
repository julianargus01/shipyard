# SHIPYARD.

**Learn AI. Build It. Ship It.**

> Most AI beginners don't fail to build — they fail to start.

Shipyard is a folder-based AI coach that takes you from "I want to use AI" to **one shipped, show-offable project.** Not a tutorial. Not a chatbot. A coach that pushes back, kills scope creep, and refuses to do the work for you.

**[Try the live demo →](https://shipyard-coach.workers.dev)** (no signup, works on phone)

**[View the landing page →](https://julianargus01.github.io/shipyard/)**

---

## The Problem

Most people who want to use AI get stuck in one of three places:

1. **"I don't know where to start."** They've been sitting with an idea for months. Not because they can't build — because they never got a clear starting point.
2. **"I built something but never shipped it."** The tool exists in a folder somewhere. It needed one more thing. Then another.
3. **"I shipped something but can't explain it."** No writeup. No post. No one knows it exists.

Shipyard coaches through all three.

---

## What This Coach Does

- **Step Protocol** — every step follows Teach → Assign → Review → Correct → Approve. No skipping.
- **Socratic Correction** — states *why* you missed before asking the next question. Never just "try again."
- **Knowledge Gap Detection** — when you say "I don't know," it stops asking and teaches.
- **Scope Kill** — propose 5 features? The redirect IS the turn. Everything else goes to V2.
- **One-at-a-Time File Building** — never builds the whole thing at once. One field, one confirmation.
- **Gate Criteria** — cannot advance to the next phase until every checkpoint passes.

## What This Coach Refuses

- Making decisions for you (which project, which feature, what to keep)
- Letting you be a passive observer — you run, test, and report back
- Explaining more than one concept per stuck moment
- Letting a session end with no action taken
- Validating scope expansion
- Apologizing for holding the line

---

## 7 Coaching Phases

| Phase | What happens |
|-------|-------------|
| 0 — Settle | Defuse overwhelm. Set one promise: "You leave with one shipped thing." |
| 1 — Find Your Edge | Surface what makes you the right person to build this. |
| 2 — Pick ONE | Lock one project. Kill everything else. |
| 3 — Define Done | Lock the smallest working version + binary success test. |
| 4 — Build | Coach through blockers. Scaffold minimally. Hand rep back. |
| 5 — Ship | Name the stall. "Does it work? Ship it." |
| 6 — Show | One writeup. One post. You write it, the coach shapes it. |

---

## Folder Map

```
shipyard/
├── identity.md       who the Shipwright is, beliefs, opening move
├── rules.md          8 rules, step protocol, stage map, phase routing
├── examples.md       coaching examples per phase
├── README.md         how to load and use
└── reference/
    ├── phase-0-settle/
    ├── phase-1-find-your-edge/
    ├── phase-2-pick-one/
    ├── phase-3-define-done/
    ├── phase-4-build/
    ├── phase-5-ship/
    └── phase-6-show/
```

Each phase subfolder contains: `identity.md`, `rules.md`, `examples.md`, `reference.md`

---

## 5-Minute Test

Verify it's actually coaching, not lecturing.

### Test 1: Opening Move
**Do:** Load the folder into a Claude project. Say nothing.
**Expect:** The Shipwright opens with a specific greeting and one question. NOT "How can I help you?"

### Test 2: Scope Kill
**Do:** After Phase 1, say: "I want to build a full SaaS platform with user auth, payments, a dashboard, and an AI assistant."
**Expect:** Scope redirect as its own turn. Does NOT start planning the complex version.

### Test 3: Knowledge Gap
**Do:** Answer any question with: "I don't know, you tell me."
**Expect:** Stops asking. Teaches in 1-2 sentences. Re-assigns a simpler version. Does NOT ask another question.

See [ASSESSOR_GUIDE.md](ASSESSOR_GUIDE.md) for the full judge protocol.

---

## Setup (2 minutes)

### Option 1: Claude Projects (recommended)
1. Clone this repo: `git clone https://github.com/julianargus01/shipyard`
2. Open [Claude.ai](https://claude.ai) → Create a new Project
3. Upload the entire `shipyard/` folder as Project Knowledge
4. Start a new conversation. The Shipwright opens immediately.

### Option 2: Claude Code
1. Clone the repo
2. Open the folder in Claude Code
3. Tell Claude: `"Read identity.md, rules.md, and examples.md, then begin."`

### Option 3: Live Demo
**[Try it now →](https://shipyard-coach.workers.dev)** — no signup, no API key, works on phone.

---

## Limits

Shipyard coaches one thing: **shipping your first AI project.** It will not:
- Teach you programming from scratch
- Coach you on non-AI projects
- Build the project for you
- Help you with job applications, resumes, or interviews
- Provide therapy or life coaching

---

## Built For

[Clief Notes Weekly Comp #5: "The Coach"](https://www.skool.com/cliefnotes/weekly-comp-5-the-coach) — a competition to build domain-specific coaching folders for Claude.

Built on the playbook method: each file does one job, the AI reads them before you say a word. The coaching arc — from finding your edge to posting the finished thing — runs through 7 phases with a locked Step Protocol.

---

## License

MIT
