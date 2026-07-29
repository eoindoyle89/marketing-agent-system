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
6. Tells you exactly what raw materials to add.
7. Verifies the folder structure before reading files.
8. Audits your public website and public-facing assets.
9. Interviews you in stages.
10. Writes durable context files that downstream marketing agents read.

## Canonical Store

The canonical source of truth is:

```text
.agent-context/
```

Do not rely on AI chat memory as company truth.

## Optional Operations Layer

Airtable, Notion, or another database can be added later for campaign calendars,
content inventories, experiment backlogs, and production tracking. They should
not own canonical positioning, proof points, case studies, brand voice, or
approval policy.
