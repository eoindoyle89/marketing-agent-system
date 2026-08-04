---
name: guide
description: >
  Show the day-to-day usage guide for the marketing-agent-system. Use when the
  user says "guide", "show guide", "how do I use this", "what should I do
  next", "help me start", or asks how to work with the system after setup.
  If no company context store exists, route to `start-here`. If setup is
  complete, explain that users should normally start with
  `marketing-orchestrator`, unless they know the exact specialist skill they
  need.
---

# Guide

Show the user how to use the marketing-agent-system day to day.

## Instructions

1. Read `../GUIDE.md`.
2. Check whether a `.agent-context/INDEX.md` context store is available in the
   current working directory or parent folders.
3. If no context store exists, tell the user this is first-time setup and route
   them to:

```text
Use start-here.
```

4. If a context store exists and the user has not described a task yet, tell
   them to start with:

```text
Use marketing-orchestrator. I want to [describe the marketing outcome].
```

5. Do not choose a specialist skill unless the user's task is already clear.
6. Do not publish, send, spend, contact, approve claims, or change live systems.

## Default Output

When the user simply asks for the guide, show:

- first-time vs after-setup starting point;
- common starting prompts;
- when to use specific skills directly;
- the approval reminder.

Keep it short enough to be useful in chat. Link back to `GUIDE.md` when a local
file link is available.
