# Decision Helper — Routing

## Input

Paste in: the decision you're stuck on, the options you're considering, and any factors or constraints you're already aware of. One paste, plain text, no special format required.

## Flow

```
pasted input
  → Frame    (clarify the real decision, enumerate options + factors, surface hidden ones)
  → Weigh    (rate each option High/Med/Low against context.md priorities in order — this is where your judgment lives)
  → Recommend (recommendation + reasoning + runner-up + what would flip it)
```

## Key dependency

The Weigh and Recommend steps both read `context.md` in your `decision-helper` folder. That file holds your priorities, priority order, and dealbreakers. Personalize it before your first run; results are only as good as the criteria you put in.

## Single-session use

All three stages run in one conversation. No state is stored between sessions. Paste your decision fresh each time.
