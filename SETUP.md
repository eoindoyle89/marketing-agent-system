# Setup

The recommended setup is a private GitHub repo cloned locally, with company
marketing context stored as Markdown under `.agent-context/`.

You do not need to know GitHub before using this system. The
`marketing-system-setup` skill is designed to guide you through each step.

## What The Setup Agent Does

1. Explains the information-store model.
2. Helps you create or choose a private GitHub context repo.
3. Helps clone it locally, or chooses a local-only fallback if GitHub is not
   available yet.
4. Creates `.agent-context/`.
5. Creates `.agent-context/inbox/` and `.agent-context/attachments/`.
6. Verifies the folder structure.
7. Audits your public website, social accounts, and public-facing assets first.
8. Shows source-level public capture before giving a confident public summary.
9. Shows what the market can already see.
10. Then asks which private/internal source pool to use.
11. Accepts `.agent-context/inbox/`, an existing Obsidian vault, a local
    folder, synced drive export, system export, chat attachments, or individual
    files.
12. Presents contradictions and information gaps.
13. Interviews you in stages.
14. Writes durable context files that downstream marketing agents read.

## Stage 1 Context Build

After the information store exists, the setup agent builds the first usable
marketing context.

It will:

1. Ask for your website, social accounts, and public-facing assets.
2. Index public assets in `.agent-context/sources.md`.
3. Summarize observed public messaging in
   `.agent-context/public-asset-audit.md`.
4. Complete a source-capture gate so the readout does not sound more certain
   than the evidence allows.
5. Show a public readout before requesting private/internal material.
6. Ask which private/internal source pool to use.
7. Index private/internal files in `.agent-context/sources.md`.
8. Present contradictions between public assets, private sources, and current
   context.
9. Ask targeted questions to resolve high-risk gaps.
10. Show a source map before drafting canonical context.
11. Interview you across company/product, customer research, positioning,
    competitors, offers/pricing, measurement, brand, proof, channels,
    operations, campaign history, and QA instead of sending a giant
    questionnaire.
12. Draft one context domain at a time.
13. Ask before promoting inferred facts.
14. Record approvals immediately when you approve a file, section, claim, or
    scoped output.
15. Put public-facing claims in `.agent-context/proof-points.md` with source,
   status, allowed wording, and forbidden overclaims.
16. Store reusable case studies in `.agent-context/case-studies.md`.
17. Write downstream read rules in `.agent-context/INDEX.md`.

Public assets are treated as observations. They are not automatically approved
company truth.

## Skill-Aligned Context Files

The setup documents are designed to mirror the installed skills they will later
feed.

The context store covers:

- company, product, capabilities, journey, positioning, ICP, and customer
  research;
- competitors, offers, pricing, goals, funnel definitions, measurement, and
  campaign history;
- brand voice, anti-AI writing rules, visual identity, channel rules, and
  marketing operations;
- proof points, case studies, QA policy, source provenance, approvals, and open
  questions.

Every task starts with `.agent-context/INDEX.md`, which routes the agent to the
required and conditional files for that task.

Downstream agents use the shared read contract in
`shared/context-read-protocol.md`: read the index first, classify the task,
load only the required context, check proof and approval boundaries, and report
limits before any public-facing use.

After setup, return to [GUIDE.md](GUIDE.md). For day-to-day work, start with:

```text
Use marketing-orchestrator. I want to [describe the marketing outcome].
```

To bring the usage guide back in chat, ask:

```text
Use guide.
```

## Canonical Store

The canonical source of truth is:

```text
.agent-context/
```

Do not rely on AI chat memory as company truth.

Raw source material can live wherever it is easiest and safest for the user:
`.agent-context/inbox/`, an Obsidian vault, a local folder, a synced drive
export, a system export, chat attachments, or individual files. The setup agent
records the approved source pool and writes the distilled, approved context into
`.agent-context/`. Chat attachments used as ongoing evidence should be copied
locally or summarized with source IDs so future agents do not depend on chat
memory.

## Optional Operations Layer

Airtable, Notion, or another database can be added later for campaign calendars,
content inventories, experiment backlogs, and production tracking. They should
not own canonical positioning, proof points, case studies, brand voice, or
approval policy.
