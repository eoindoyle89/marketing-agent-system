# Guide

Use this guide to choose the right starting point.

## First Time

```text
Use start-here.
```

Use this if you have just installed the repo, pasted the repo URL into your AI,
or do not yet have a company context store.

`start-here` explains what the system is, who created it, how it works, and why
setup comes first. It then routes into `marketing-system-setup`, the context
gathering agent.

## After Setup

Once your company context store exists, start every normal marketing request
with:

```text
Use marketing-orchestrator. I want to [describe the marketing outcome].
```

If you need this guide again, ask:

```text
Use guide.
```

## The Simple Rule

First time: use `start-here`.

After setup: use `marketing-orchestrator` unless you already know the exact
skill you want.

You do not need to know the skill list, the `.agent-context/` file map, or which
approval gate applies. The orchestrator figures out the route.

## What To Give The System

You can start with any useful input:

- a goal: "We need more demo requests";
- a source: a URL, file, folder, export, pasted text, or attachment;
- a draft: a post, email, ad, landing page, brief, or idea;
- a change: a new case study, pricing change, feature launch, campaign result,
  approval, or retired claim;
- a problem: "This journey feels confusing" or "people are dropping off";
- a task: "Create a campaign around this."

## The Normal Workflow

```text
You
  -> marketing-orchestrator
  -> context-update if company truth changed
  -> campaign-planner if the work is campaign-shaped
  -> marketing-ux if the journey has friction or unclear handoffs
  -> specialist skills for production
  -> review gates
  -> human approval
```

Agents may draft, analyse, plan, and review. They do not publish, send, spend,
contact, approve claims, or change live systems.

## Common Starting Prompts

```text
Use marketing-orchestrator. We have a new approved case study and I want to
promote it.
```

```text
Use marketing-orchestrator. I want to improve the journey from this LinkedIn
post to a demo request.
```

```text
Use marketing-orchestrator. Here is a draft post. Tell me what should happen
next before I publish it.
```

```text
Use marketing-orchestrator. Our pricing changed. Update the system before we
create any new marketing.
```

```text
Use marketing-orchestrator. Plan a campaign for this launch, then stop before
creating assets.
```

## When To Use Specific Skills Directly

Use a specific skill directly only when the task is obvious:

| If you need | Use |
|---|---|
| Set up company context | `marketing-system-setup` |
| Add new company truth | `context-update` |
| Plan a campaign | `campaign-planner` |
| Improve a journey across touchpoints | `marketing-ux` |
| Write a LinkedIn article | `linkedin-article-ghostwriter` |
| Review a LinkedIn article | `linkedin-article-reviewer` |
| Review a LinkedIn post | `linkedin-post-reviewer` |
| Full marketing roadmap | `marketing-plan` |
| Landing page or conversion review | `cro` |
| Emails or nurture | `emails` |

When unsure, use `marketing-orchestrator`.

## New Information

If something changed, say so plainly:

```text
Use marketing-orchestrator. This is new approved information: [paste or attach].
```

The orchestrator should route through `context-update` before any production
work. That keeps future agents from relying on chat memory.

## Approvals

Approval is always scoped.

Useful approval language:

```text
Approved for internal planning only.
```

```text
Approved for public use on LinkedIn, but do not use the customer logo.
```

```text
Approved for this campaign only. Do not make it a general proof point.
```

```text
This claim is retired. Do not use it again.
```

## If The System Stops

If an agent stops and asks a question, it should be because the missing answer
changes safety, strategy, proof, approval, or the next step.

Good answers are short:

```text
Use the case study for LinkedIn and email only. Approved by Maya on 2026-08-04.
```

```text
No paid ads for this campaign. Organic LinkedIn and sales follow-up only.
```

```text
Proceed with limitations. Do not use the unapproved metric.
```

## What Good Looks Like

A good run should end with:

- what was created or reviewed;
- what context was used;
- what context changed;
- what claims were allowed or excluded;
- what still needs human approval;
- what the recommended next step is.

If that is missing, ask:

```text
Summarize the context used, limits, approvals needed, and next step.
```
