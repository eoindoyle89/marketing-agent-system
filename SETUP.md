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
8. Shows what the market can already see.
9. Then asks for private/internal source material.
10. Presents contradictions and information gaps.
11. Interviews you in stages.
12. Writes durable context files that downstream marketing agents read.

## Stage 1 Context Build

After the information store exists, the setup agent builds the first usable
marketing context.

It will:

1. Ask for your website, social accounts, and public-facing assets.
2. Index public assets in `.agent-context/sources.md`.
3. Summarize observed public messaging in
   `.agent-context/public-asset-audit.md`.
4. Show a public readout before requesting private/internal material.
5. Ask you to add private/internal files to `.agent-context/inbox/`.
6. Index private/internal files in `.agent-context/sources.md`.
7. Present contradictions between public assets, private sources, and current
   context.
8. Ask targeted questions to resolve high-risk gaps.
9. Show a source map before drafting canonical context.
10. Interview you in stages instead of sending a giant questionnaire.
11. Draft one context file at a time.
12. Ask before promoting inferred facts.
13. Put public-facing claims in `.agent-context/proof-points.md` with source,
   status, allowed wording, and forbidden overclaims.
14. Store reusable case studies in `.agent-context/case-studies.md`.
15. Write downstream read rules in `.agent-context/INDEX.md`.

Public assets are treated as observations. They are not automatically approved
company truth.

## Skill-Aligned Context Files

The setup documents are designed to mirror the installed skills they will later
feed. For brand voice, `.agent-context/brand-voice.md` captures the same
operational surface that a brand-voice generation/enforcement skill needs:
positioning, audience, voice constants, tone flexes, do/don't rewrites,
terminology, mechanics, messaging pillars, formatting conventions, worked
examples, edge cases, confidence, and open questions.

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
