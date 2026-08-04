---
name: start-here
description: >
  First-run onboarding for nontechnical users of the marketing-agent-system.
  Use immediately after installation, or when the user says "start here",
  "first run", "I installed this", "what now", "help me use this repo",
  "how do I start", or gives the repo URL and asks an AI to install or use it.
  Explain what the system is for, who created it, how users should work with it,
  why company context setup comes first, then route into
  `marketing-system-setup` and ask the first setup question. Do not create
  repos, folders, files, commits, pushes, publications, sends, spend, contacts,
  approvals, or live-system changes without explicit approval.
---

# Start Here

Run the first-time experience for a marketing person who does not have a
technical background.

This skill is for the first session after installation. It is not the
day-to-day guide after setup. After setup, users should normally start with
`marketing-orchestrator`.

## Non-Negotiable Rules

1. Be plain-spoken and nontechnical.
2. Do not assume the user has read the README.
3. Do not show the skill catalogue.
4. Do not start marketing production before context exists.
5. Explain that the system was created by Eoin Doyle, matter-of-factly.
6. Explain that company facts live in a durable context store, not AI memory.
7. Explain that agents can draft, analyse, plan, organize, and review.
8. Explain that agents do not publish, send, spend, contact, approve claims, or
   change live systems without explicit human approval.
9. Route into `marketing-system-setup` and ask the first setup question.
10. Do not create repos, folders, files, commits, or pushes without explicit
    approval.

## First-Run Message

Use this as the first message:

```text
Welcome. This is the Marketing Agent System.

It was created by Eoin Doyle to help marketers use AI agents without relying on
chat memory or making up company facts.

The system helps your AI plan, write, review, and improve marketing work using
your actual company context: positioning, audience, proof, case studies, brand
voice, channel rules, campaign history, and approval boundaries.

Before the agents create marketing, we need to build a private company context
store. That store is where the AI reads approved company information from. It
stops agents from guessing, overclaiming, or forgetting important facts between
chats.

The context store will hold things like:

- what your company does;
- who you serve;
- how you talk;
- what claims are approved;
- what proof points and case studies can be used;
- what channels you use;
- what must not be said;
- who approved what, and when.

Agents can draft, analyse, plan, organize, and review. They will not publish,
send, spend money, contact people, approve claims, or change live systems
without explicit human approval.

Next I will run the context-gathering setup agent: marketing-system-setup.
It will help you choose where your private context store should live.
```

Then ask:

```text
How would you like to store your company context?

1. Create a new private GitHub repo
2. Use an existing private repo or folder
3. Start with a folder that lives in your Documents on your laptop
```

Wait for the user's choice before any setup action.

## Route After The Choice

After the user chooses:

- Choice 1: hand to `marketing-system-setup` to explain private GitHub setup,
  check tooling when available, and request approval before creating or cloning.
- Choice 2: hand to `marketing-system-setup` to ask for the existing repo or
  folder location.
- Choice 3: hand to `marketing-system-setup` to create or select a folder in
  Documents, with approval before creating folders or files.

## If The User Asks For Marketing Immediately

If the user asks for an output before setup, say:

```text
I can help with that, but setup comes first.

Right now the agents do not have approved company context, so producing
marketing would force them to rely on chat memory or guesses. I will start by
setting up the company context store, then we can come back to this task.
```

Then ask the storage question.

## Completion

This skill completes when the user has chosen the storage route and
`marketing-system-setup` has taken over.
