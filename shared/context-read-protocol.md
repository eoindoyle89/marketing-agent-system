# Shared Agent Context Read Protocol

Use this protocol in every downstream marketing skill that reads a company's
`.agent-context/` store.

## Purpose

Make marketing agents context-aware without letting them overread, invent
missing company truth, or treat public observations as approved claims.

The agent's job is to load the smallest complete context set for the task, obey
approval boundaries, and report any limitation that changes what can safely be
produced.

## Protocol Version

- Version: `v0.2`
- Status: Draft local contract
- Owner: Marketing Agent System

## Required Flow

1. Locate the company context store.
2. Read `.agent-context/INDEX.md` first.
3. Classify the user request into one task family from the index.
4. Read the core files and task-family files listed by the index.
5. Read conditional files only when the request triggers them.
6. Build a short context ledger before producing output.
7. Run the First-Principles Task Check.
8. Check claim, approval, freshness, restriction, and contradiction boundaries.
9. Ask only for missing information that blocks the specific task.
10. Produce the requested output only inside the approved context boundaries.
11. Report limitations, open questions, and any context updates needed.

## Store Discovery

When the user has not given a path:

- Check the current working directory for `.agent-context/INDEX.md`.
- Check parent directories up to the repo or vault root.
- If multiple context stores are found, ask which company/context to use.
- If none is found, ask for the local path or recommend running
  `marketing-system-setup`.

Do not proceed from chat memory alone.

## Context Ledger

Before drafting, reviewing, planning, or analysing, maintain a task-local ledger:

```text
Context ledger:
- Context path:
- Index status:
- Task family:
- Core files read:
- Required files read:
- Conditional files read:
- Approved claims available:
- Use-with-boundary claims available:
- Restricted or stale inputs excluded:
- Contradictions affecting this task:
- Missing inputs that block the task:
- Missing inputs that do not block the task:
```

The final answer can summarize this ledger briefly; it does not need to dump the
whole ledger unless the user asks.

## First-Principles Task Check

After context loading and before drafting, reviewing, planning, analysing, or
recommending, decompose the task from first principles. Do this even when the
user names a specialist skill directly.

Use the smallest version that is useful for the task:

```text
First-principles task check:
- Stated request:
- Real deliverable:
- Underlying business outcome:
- Audience or stakeholder:
- Current state:
- Desired state:
- Primary blocker:
- Context, proof, or approval limits:
- Smallest useful output:
- Blocking questions:
- Assumptions if proceeding:
```

Ask questions only when the missing answer changes the safe next step. If the
task can proceed safely, label the assumptions and keep the output inside the
approved context boundaries.

If a specialist skill defines a stricter first-principles, routing, campaign, or
journey diagnosis, use the stricter skill-specific version while preserving this
check's intent.

## File Status Rules

- `Approved`: usable inside the stated scope and review date.
- `Usable with limitations`: usable only for named tasks and limits.
- `Draft`: internal reasoning only unless the task can tolerate draft context.
- `Review due`: ask whether to refresh before using for public-facing output.
- `Not started`: treat as missing.

If a required file is missing, `Not started`, stale, or contradicted, decide
whether that blocks the task. A lightweight brainstorm may continue with labels;
public-facing copy with factual claims usually blocks.

## Claim Rules

Use `proof-points.md` as the public-claim ledger.

- Use `Approved` claims as written or within allowed wording.
- Use `Use With Boundary` claims only with the recorded qualifier.
- Do not use `Unverified`, `Contradicted`, or `Retired` claims in
  public-facing output.
- Do not turn `public-asset-audit.md`, social engagement, a case-study draft, or
  a private source into a public claim unless `proof-points.md` allows it.
- If a claim is needed but not approved, ask for approval or write around it.

## Source And Evidence Rules

- Use `sources.md` for provenance, authority, approval, freshness,
  confidentiality, permissions, and source-pool boundaries.
- Read only source pools explicitly approved in `sources.md` or by the user in
  the current task.
- For chat attachments, use only attachments identified by the user and record
  that future use needs a durable local copy or source-backed summary.
- Never expose restricted source material in public-facing output.
- Quote only short excerpts when exact wording matters.

## Conflict Rules

If context conflicts:

1. Prefer the current approved source with the clearest authority.
2. Prefer system-of-record exports for numbers, dates, customers, pipeline, and
   revenue.
3. Treat public assets as observed market-facing messaging, not company truth.
4. If the conflict affects the task outcome, stop and ask.
5. If it does not block the task, proceed with a visible limitation and add the
   issue to `open-questions.md` when file edits are in scope.

Do not silently choose the version that makes better copy.

## Task Family Routing

Use the task-family table in `.agent-context/INDEX.md` as the source of truth.

When a request fits multiple task families:

- Pick the primary family based on the output the user asked for.
- Add conditional reads for secondary risks.
- For external-facing output, always include brand voice, anti-AI rules,
  channel rules, proof points, and QA policy.

## Production Boundaries

Downstream agents may draft, critique, plan, analyse, and recommend.

They may not:

- publish;
- send;
- submit;
- spend money;
- change live campaigns;
- contact prospects or customers;
- approve claims on behalf of the user.

If the user approves something during the task and file edits are in scope,
record the approval immediately in the relevant context file and
`changelog.md`.

## Missing Context Behaviour

Ask for more information only when it materially affects the task.

Use this decision rule:

- `BLOCKED`: missing or conflicted context would make the output unsafe,
  misleading, off-brand, or unusable.
- `PROCEED WITH LIMITATIONS`: the task can be completed if assumptions are
  tagged and risky claims are omitted.
- `PROCEED`: the missing context is not material to this task.

## Output Footer

For substantive tasks, end with a compact context note:

```text
Context used: [files]
Limits: [none / specific missing, stale, or excluded context]
Needs update: [context files or open questions]
Approval required before: [publish/send/claim use/etc.]
```

Keep the footer short. The goal is traceability, not paperwork.
