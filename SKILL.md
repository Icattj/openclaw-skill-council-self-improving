---
name: Council Self-Improving
description: Agent picks up patterns from how Lucy interacts and quietly improves how it responds to her specifically. Logs corrections, preferences, and patterns. Promotes patterns that repeat 3+ times to HOT memory (always loaded). Use after corrections, after significant work, or when you notice your output could be better.
---

# Council Self-Improving

Learns from corrections. Stores preferences in local files. Improves permanently.

## Memory Structure

```
~/self-improving/
├── memory.md          # HOT: ≤100 lines, always loaded first
├── corrections.md     # Last 50 corrections log  
├── index.md           # Topic index
├── projects/          # Per-project learnings
│   ├── council-room.md
│   └── dataflow.md
├── domains/           # Domain-specific patterns
│   ├── code.md        # Code style, tools, preferences
│   └── comms.md       # Communication patterns
└── archive/           # Cold: unused 90+ days
```

## When to Log

**Always log:**
- Lucy says "No, that's wrong..."
- Lucy says "I prefer X, not Y"
- Lucy says "Stop doing X"
- Lucy says "Remember that I always..."
- Same instruction repeated 3+ times

**Promote to HOT (memory.md) after 3x confirmation**

**Never log:**
- One-time context-specific instructions
- Transient states (current time, temp data)
- Credentials or sensitive info

## Log Format

```
CORRECTIONS LOG entry:
Date: YYYY-MM-DD
Context: [what I was doing]
Got wrong: [what I did]
Correct: [what I should do]
Status: logged|promoted|archived
```

## Self-Reflection Trigger

After completing significant work, briefly check:
1. Did it meet expectations?
2. What could be better?
3. Is this a repeating pattern? → log to corrections.md

## HOT Memory — Always Load

Before every non-trivial response, read `~/self-improving/memory.md` (≤100 lines).
This is your persistent preferences layer for Lucy specifically.

## Tier Rules

| Tier | File | Size | Load |
|------|------|------|------|
| HOT | memory.md | ≤100 lines | Always |
| WARM | projects/*.md, domains/*.md | ≤200 lines each | On context match |
| COLD | archive/ | Unlimited | On explicit query |

Pattern used 3x in 7 days → promote to HOT
Pattern unused 30 days → demote to WARM  
Pattern unused 90 days → archive
Never delete without asking

## Lucy's Current HOT Memory

Maintained in `~/self-improving/memory.md` — read it before responding.
