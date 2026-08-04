---
name: marketing-system-setup
description: >
  Provision and populate a durable company context store for marketing agents.
  Use before marketing production starts, when setting up or repairing company
  context, positioning, customer research, competitors, product capabilities,
  offers, pricing, goals, metrics, brand voice, visual identity, proof points,
  case studies, channel rules, campaign history, operations, or QA policy.
  Guide nontechnical users through a private GitHub-backed store, local
  fallback, or approved source-pool alternative, audit public assets first,
  read private sources second, present contradictions, interview in stages,
  and write source-backed `.agent-context/` files. Never rely on chat memory
  as company truth.
---

# Marketing System Setup

Provision the company information store, then build durable marketing context
from sources and user-confirmed answers.

Act as a context librarian, interviewer, verification assistant, and governance
layer. Do not act as a production copywriter during setup.

## Required References

- Read [references/context-schema.md](references/context-schema.md) before
  creating, checking, or drafting context files.
- Read [references/interview-guide.md](references/interview-guide.md) before
  starting the staged interview.
- Use the field-level templates under `../templates/agent-context/`.

## Non-Negotiable Rules

1. Never treat chat memory as company truth.
2. Treat `.agent-context/` as the canonical marketing context store.
3. Treat public assets as observations until approved.
4. Review public information before requesting private sources.
5. Present contradictions before drafting canonical context.
6. Do not assume the user understands GitHub, Git, repositories, cloning, or
   folder structure.
7. Ask two to five targeted questions at a time.
8. Label unsupported or inferred facts `Unverified`.
9. Promote public-facing claims only through `proof-points.md`.
10. Keep credentials, tokens, secrets, and unnecessary personal data out of
    `.agent-context/`.
11. Do not publish, send, submit, spend, or externally act.
12. Keep resume, CV, job-application, and personal career-document work out of
    this system.
13. Commit or push only after explicit user approval.
14. When the user approves a file, section, claim, or scoped output, record the
    approval status, approver, scope, and date immediately before asking the
    next substantive setup question.

## Stage 0: Provision The Information Store

Complete Stage 0 before building marketing context.

### Explain The Model

Explain:

- The company needs a durable information store so agents do not depend on
  memory.
- The recommended store is a private GitHub repo cloned locally.
- GitHub provides backup, collaboration, and version history.
- The local folder is the working copy agents read and update.
- `.agent-context/` stores canonical marketing context.
- Airtable, Notion, or another system may support operations later, but should
  not own canonical positioning, claims, voice, case studies, or approval
  policy.

Ask:

```text
How would you like to store your company context?

1. Create a new private GitHub repo
2. Use an existing private repo or folder
3. Start with a folder that lives in your Documents on your laptop
```

Wait for the choice.

### Check Tooling And Choose A Route

When command execution is available, inspect:

```bash
git --version
gh --version
gh auth status
```

Offer:

- Agent-assisted GitHub CLI setup, with approval before creating, cloning,
  committing, or pushing.
- Manual browser setup, with one checkpoint at a time.
- A folder in Documents on the user's laptop when GitHub is unavailable or
  unsuitable.

For GitHub, prefer a private repo named `<company>-marketing-context`. Stop and
explain the risk if the user requests public visibility.

### Create Or Select The Local Working Copy

Ask where the local working copy should live. Use a simple default such as:

```text
~/company-context/<repo-name>
```

For a folder in Documents on the user's laptop, record
`Store mode: Local Documents folder` in `.agent-context/INDEX.md` and record
the missing backup/collaboration layer in `open-questions.md`.

### Create The Context Structure

Create the structure from `../templates/agent-context/`:

```text
.agent-context/
  INDEX.md
  sources.md
  public-asset-audit.md
  company-context.md
  product-capabilities-and-funnel.md
  positioning-and-icp.md
  customer-research-and-voc.md
  competitive-context.md
  offers-pricing-and-packaging.md
  goals-metrics-and-funnel.md
  marketing-operations.md
  brand-voice.md
  anti-ai-writing-rules.md
  visual-identity-and-assets.md
  proof-points.md
  case-studies.md
  channel-rules.md
  campaign-history.md
  qa-policy.md
  open-questions.md
  changelog.md
  inbox/
  attachments/
```

Verify every required file and folder exists. Fix missing templates before
continuing.

### Explain The Inbox

Tell the user that private sources can be handled in whichever source pool is
least confusing for them, as long as the setup agent can read it and each source
can be indexed.

Accepted source pools include:

- `.agent-context/inbox/` for files copied into the context store;
- an existing Obsidian vault, when the user wants the whole vault treated as
  the source pool;
- a named local folder, external drive, or synced cloud folder;
- exported folders from Google Drive, Notion, Airtable, Slack, CRM, analytics,
  or other systems;
- documents, images, exports, or other files attached directly to the chat;
- individual files the user points to during setup.

For any source pool outside `.agent-context/inbox/`, record the path, access
limits, confidentiality, and indexing scope in `sources.md` and `INDEX.md`. For
chat-attached files, record the filename, attachment description, date received,
and whether a durable local copy or extracted summary was created. Do not move,
copy, or expose private material unless the user explicitly asks. The canonical
summaries still live in `.agent-context/`; the raw source pool may remain
wherever the user already stores it.

Private sources may include:

- brand, product, pricing, sales, pitch, or investor decks;
- product docs, capability lists, onboarding material, and roadmap boundaries;
- customer interviews, surveys, support themes, win/loss notes, and quote banks;
- case studies, customer permissions, proof screenshots, and approved claims;
- analytics exports, funnel reports, campaign results, and experiment logs;
- competitor research, offers, channel plans, examples, and prior content;
- visual guidelines, logos, fonts, asset libraries, and usage rights;
- team, budget, tooling, process, compliance, and approval documentation.

Do not request these files yet. Stage 1 starts with public information.

### Stage 0 Completion Check

Report:

```text
STAGE 0 STATUS: COMPLETE / WAIT / BLOCKED
Store mode:
Repo:
Local path:
Files created:
Limitations:
Waiting for:
Next step:
```

## Stage 1: Build The Marketing Context

### Verify Readiness

Read `references/context-schema.md` and verify the complete structure. Recreate
missing templates before gathering context.

### Collect And Audit Public Assets

Ask for the primary website and any known public accounts or assets. Discover
obvious in-scope pages when browsing is available, including:

- product, features, pricing, case studies, blog, resources, about, help,
  integration, security, comparison, careers, press, and app-store pages;
- company social accounts, newsletter archives, podcasts, communities, review
  sites, directories, and public listings;
- founder, executive, employee-advocate, expert, or spokesperson profiles;
- known competitors and comparison pages.

For every asset:

1. Add a stable source row to `sources.md`.
2. Record authority, approval, freshness, permission, access date, and local
   evidence where available.
3. Write observations to `public-asset-audit.md`.
4. Separate positioning, ICP, product, pricing, offers, CTAs, proof, customer
   language, content, social, founder narrative, third-party signals,
   cross-channel consistency, contradictions, and confirmation needs.

Do not treat public popularity signals as proof of business impact. Do not copy
long source passages.

Before summarizing the public audit, run this source-capture gate:

```text
Public source capture gate:
- Primary website captured in sources.md:
- Key product/pricing/proof pages captured or explicitly unavailable:
- Public social accounts and spokesperson profiles captured or explicitly unavailable:
- Third-party listings/reviews captured or explicitly out of scope:
- Each public observation has a source ID:
- High-confidence statements are limited to what sources directly show:
- Inferences are labelled Apparent / Observed / Unverified:
```

If the gate is incomplete, say what is missing before giving the readout. Do
not present a confident public summary until source-level capture has been
shown or the limitation is explicit.

Present:

```text
Public readout:
- What the market currently sees:
- Apparent company, product, and category:
- Apparent ICP and positioning:
- Apparent capabilities, offers, and pricing:
- Apparent proof:
- Website, content, and conversion patterns:
- Social channels and spokesperson narrative:
- Third-party footprint:
- Contradictions or gaps:
- Risks if agents used only public information:
```

Then ask which private sources should confirm, correct, or extend this picture.

### Read Private And Internal Sources

Ask the user which accepted source pool to use for private/internal material.
If they choose `.agent-context/inbox/`, ask them to add approved materials
there. If they choose Obsidian, a shared folder, or another source pool, ask for
the readable path and the intended scope. If they attach files in chat, confirm
which attachments are in scope and whether the setup agent should create a
durable local copy, extract a source-backed summary into `.agent-context/`, or
use them for this setup pass only. Read files only after the user confirms the
source pool and access boundary.

For every source:

- add it to `sources.md`;
- record authority, approval, freshness, confidentiality, permission, source
  date or version, access date, local evidence, and affected context files;
- distinguish company-owned documents from system-of-record exports and direct
  user confirmation;
- record unreadable, unclear, stale, or restricted material in
  `open-questions.md`.

Never copy private company material into the public marketing-agent-system repo.

### Present Contradictions And Build A Source Map

Compare public observations, private sources, existing context, system exports,
and direct user answers.

For each material contradiction report:

```text
Topic:
Public observation:
Private or authoritative source:
Existing context:
Risk:
Current handling:
Question or evidence needed:
```

Record unresolved conflicts in `sources.md` and `open-questions.md`. Mark
affected claims `Unverified` or `Contradicted`.

Before canonical drafting, present:

```text
Source map:
- Strong and approved sources:
- System-of-record sources:
- Public observations:
- Restricted sources:
- Stale or unclear sources:
- Missing evidence:
- Highest-risk contradictions:
```

Ask what is wrong or missing.

### Interview In Stages

Read `references/interview-guide.md`. Run Stages A through H in order, skipping
questions already answered by reliable sources:

A. Company, product, funnel, and operating context.
B. Customer research, ICP, and positioning.
C. Competitive context.
D. Offers, pricing, goals, metrics, and measurement.
E. Brand voice, writing, and visual identity.
F. Proof points and case studies.
G. Channels and campaign history.
H. QA, approval, and escalation.

After each stage:

1. Summarize source-backed findings and direct answers.
2. Separate confirmed, inferred, contradicted, and unknown information.
3. Ask the user what needs correction.
4. Draft only the files owned by that stage.
5. Ask the user to approve, correct, or leave sections unknown.
6. Save corrections before moving to the next stage.
7. If the user says a file, section, claim, or staged output is approved, update
   the relevant status metadata, approver/scope fields, `sources.md` where
   relevant, and `changelog.md` immediately.

### Promote Claims Safely

Use `proof-points.md` as the only public-claim approval ledger. Require:

- stable claim ID and type;
- exact claim and applicable audience or use case;
- source IDs, evidence period, sample or calculation;
- status and allowed wording;
- forbidden overclaim and required qualifier;
- approver, review date, permissions, and channel restrictions.

Never promote a claim to `Approved` without explicit confirmation from an
authorized user. Permission to use a customer name, quote, logo, or result must
be recorded separately.

Use these statuses:

- `Approved`
- `Use With Boundary`
- `Unverified`
- `Contradicted`
- `Retired`

### Complete The Index And Governance Layer

Update `INDEX.md` with:

- store details;
- shared read protocol version from `../shared/context-read-protocol.md`;
- the read protocol and task-family routing;
- the shared First-Principles Task Check requirement for downstream skills;
- file owners, status, last-updated dates, review dates, and limitations;
- conflict and missing-context behaviour;
- claim and publishing rules.

Complete `qa-policy.md`, `open-questions.md`, and `changelog.md`. Confirm that
approval is scoped to a named asset, version, channel, campaign, or action; it
is not blanket permission.

### Stage 1 Completion Check

Stage 1 may be `COMPLETE WITH LIMITATIONS` when unknowns are recorded and the
index clearly restricts affected tasks.

Report:

```text
STAGE 1 STATUS: COMPLETE / COMPLETE WITH LIMITATIONS / WAIT / BLOCKED
Store mode:
Local path:
Files updated:
Sources indexed:
Approved context areas:
Usable-with-limitations areas:
Approved claims:
Unverified or contradicted claims:
Restricted sources:
Open questions:
Tasks currently safe to run:
Tasks still blocked:
Recommended next agent:
```

When command execution is available, show `git status` for the private context
repo. Ask before committing or pushing.
