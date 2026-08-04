---
name: context-update
description: >
  Update an existing `.agent-context/` company context store when company truth
  changes after setup. Use when the user provides new information, approvals,
  URLs, pasted text, chat attachments, files, folders, exports, case studies,
  proof points, pricing changes, product updates, campaign results, customer
  quotes, claim retirements, channel rules, brand changes, visual assets,
  operational changes, or says something is now approved, changed, launched,
  deprecated, expired, corrected, or newly available. Capture the source,
  classify the update, route it to the right context files, ask only targeted
  approval and permission questions, preview changes, update `sources.md`,
  affected canonical files, `INDEX.md`, and `changelog.md`, then commit local
  changes after user approval. Never rely on chat memory as company truth.
---

# Context Update

Update durable company context after initial setup. Act as an intake clerk,
source librarian, context mapper, claim governor, contradiction reviewer, UX
steward, and change recorder.

Use this skill directly when the user provides new company information. A
future orchestrator may also call it automatically when production work finds
missing, stale, or contradicted context.

## Non-Negotiable Rules

1. Never treat chat memory as company truth.
2. Read `.agent-context/INDEX.md` before updating anything.
3. Accept messy inputs; do not require the user to know the file map.
4. Treat user-provided new information as an update request, not as blanket
   approval for every public claim inside it.
5. Record source ID, access date, approval date, approver, and approval scope
   for every material update.
6. Promote reusable public claims only through `proof-points.md`.
7. Treat public URLs and published assets as source material, not automatic
   approved company truth.
8. Surface contradictions before writing canonical truth.
9. Ask two to five targeted questions at a time.
10. Show a context update preview before editing.
11. Do not draft external marketing output during context updating unless the
    user separately asks after the update is complete.
12. Do not publish, send, submit, spend, contact, or change live systems.
13. After the user approves the update preview, write the files and commit the
    local changes. Push only after explicit push approval.
14. Keep resume, CV, job-application, and personal career-document work out of
    this system.

## Intake

Let the user start anywhere. Accept:

- URLs: case studies, pricing pages, blog posts, help docs, app listings,
  reviews, press, public customer stories.
- Files: PDFs, docs, decks, CSVs, screenshots, transcripts, exports.
- Folders or paths: Obsidian vaults, Drive exports, CRM exports, analytics
  folders, local source pools.
- Pasted text: quotes, announcements, internal notes, draft claims.
- Chat attachments: documents, images, data exports.
- Direct statements: pricing changed, a feature launched, a claim expired.
- System events: campaign results, customer approval, product changes, retired
  claims.

Start by acknowledging the source and classifying it:

```text
I can update company context from this.

I think this is: [update type]
Likely affected context: [files]
Before I write anything, I need: [2-5 targeted questions]
```

## Required Read Sequence

1. Locate the context store.
2. Read `.agent-context/INDEX.md`.
3. Read `sources.md`, `open-questions.md`, and `changelog.md`.
4. Classify the update type.
5. Read only the canonical files likely affected by that update.
6. Compare the new source with existing context.
7. Ask only blocking questions about approval, permission, evidence,
   boundaries, freshness, or contradictions.

If no context store exists, stop and recommend `marketing-system-setup`.

## Update Types

| Update type | Examples | Primary files |
|---|---|---|
| New source only | Add this document as reference | `sources.md`, `INDEX.md` |
| Case study | Customer story, result, quote | `sources.md`, `case-studies.md`, `proof-points.md`, `changelog.md` |
| Proof point / claim | Metric, testimonial, logo, credential | `sources.md`, `proof-points.md`, `qa-policy.md` when needed |
| Product capability | New feature, retired feature, roadmap change | `product-capabilities-and-funnel.md`, `proof-points.md` when public |
| Positioning / ICP | New segment, category shift, customer language | `positioning-and-icp.md`, `customer-research-and-voc.md` |
| Pricing / offer | Plan, discount, guarantee, package | `offers-pricing-and-packaging.md`, `channel-rules.md` when promoted |
| Campaign result | Launch, email, paid, event, content result | `campaign-history.md`, `goals-metrics-and-funnel.md`, `proof-points.md` when public |
| Brand / voice | Approved phrasing, banned term, tone shift | `brand-voice.md`, `anti-ai-writing-rules.md` |
| Channel rule | LinkedIn rule, email consent, ad constraint | `channel-rules.md`, `qa-policy.md` |
| Visual asset / rights | Logo, screenshot, image, permission | `visual-identity-and-assets.md`, `sources.md`, `proof-points.md` when public |
| Operations / tools | Workflow, budget, owner, system change | `marketing-operations.md`, `INDEX.md` |
| Retire / contradict | Old pricing, expired claim, obsolete segment | Affected file, `proof-points.md`, `open-questions.md`, `changelog.md` |

Support all update types in v1. If multiple types apply, handle them in one
preview and one approved write pass.

## Targeted Questions

Ask only questions that materially affect safe updating.

Approval:

- Is this approved for internal use, public use, or draft only?
- Who approved it, on what date, and for what scope?

Permission:

- Can this customer name, logo, quote, screenshot, or metric be used publicly?
- Which channels, audiences, regions, or campaigns are approved?

Evidence:

- What is the measurement period, sample, or method?
- Where is the raw evidence or system of record?

Boundary:

- What should agents not claim from this?
- Does this replace, retire, or contradict older context?

Freshness:

- When did this become true?
- When should it be reviewed again?

## Preview Before Writing

Before editing files, show:

```text
CONTEXT UPDATE PREVIEW

Update type:
Source IDs to add:
Affected files:
Claims to add, update, or retire:
Case studies to add or update:
Contradictions found:
Approval scope:
Open questions:
Proposed status:
Will not do:
- Will not draft external content.
- Will not publish, send, submit, spend, contact, or change live systems.
- Will not push unless explicitly approved.
```

The user's approval of this preview is the approval gate for writing and making
a local commit. If approval is partial, write only the approved scope and record
the rest in `open-questions.md`.

## Write Rules

After approval, update the relevant files:

- `sources.md`: source ID, source type, title, URL/path/attachment identifier,
  authority, approval status, approval date, approver, approval scope,
  confidentiality, permission, freshness, source date, access date, source pool,
  and affected files.
- Canonical context files: only the fields affected by the update.
- `proof-points.md`: reusable public claims, allowed wording, forbidden
  overclaims, evidence period, approval, permissions, and review date.
- `case-studies.md`: structured customer story, permission, related proof
  points, source IDs, reusable angles, and what not to claim.
- `open-questions.md`: unresolved gaps, unapproved claims, stale inputs, and
  contradictions.
- `INDEX.md`: status, last updated date, review due date, source-pool notes, and
  any routing notes affected by the update.
- `changelog.md`: summary, source IDs, files changed, approval date, approver,
  approval scope, and follow-up needs.

Do not paste long restricted source passages into public-facing context files.
Use short excerpts only when exact wording matters and permissions allow it.

## Local Commit Rule

After approved files are written:

1. Show the files changed.
2. Run local validation available in the environment, such as `git diff --check`
   when the context store is a Git repo.
3. Commit the local changes with a clear message, for example:
   `Update context for approved case study`.
4. Report the commit SHA.
5. Do not push unless the user explicitly approves pushing.

If the context store is not a Git repo, report that no local commit was possible
and record the limitation in `changelog.md`.

## Completion Output

End with:

```text
CONTEXT UPDATE COMPLETE

Updated:
- [files]

Approved for:
- [scope]

Still not approved:
- [claims / channels / sources]

Downstream agents can now use:
- [claims / case studies / context]

Needs follow-up:
- [open questions]

Local commit:
- [SHA / not available]

Push:
- Not done unless explicitly approved
```
