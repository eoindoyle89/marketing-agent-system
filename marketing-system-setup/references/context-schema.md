# Context Schema

Use this reference when creating, checking, or updating `.agent-context/`.
Templates under `../../templates/agent-context/` are the field-level source of
truth.

## Canonical Layers

### Source And Observation Layer

- `sources.md`: provenance, authority, approval, freshness, permission,
  contradictions, and local evidence locations.
- `public-asset-audit.md`: what the market can currently observe. It is not
  automatic company truth.
- `inbox/`: raw user-provided inputs awaiting review when the user wants files
  copied into `.agent-context/`.
- `attachments/`: durable supporting evidence referenced by context files.
- External source pools: approved readable locations such as an Obsidian vault,
  shared folder, synced drive export, system export, or individual local files.
  These can provide raw evidence without being copied into `.agent-context/`.
- Chat attachments: user-provided files attached during setup. Index them as
  sources and create a durable local copy or extracted summary when they are
  used as ongoing evidence.

### Company And Market Layer

- `company-context.md`: company identity, portfolio, business model, GTM model,
  goals, priorities, and operating context.
- `product-capabilities-and-funnel.md`: current capabilities, use cases,
  customer journey, activation, integrations, constraints, and roadmap
  boundaries.
- `positioning-and-icp.md`: category, positioning, ICP, buying roles, jobs,
  pains, outcomes, alternatives, differentiation, switching dynamics,
  objections, awareness, and anti-personas.
- `customer-research-and-voc.md`: research scope, source-backed jobs, pains,
  triggers, desired outcomes, objections, alternatives, verbatim language,
  segment differences, confidence, and sample limitations.
- `competitive-context.md`: direct, secondary, indirect, and status-quo
  alternatives; competitor positioning, pricing, strengths, weaknesses,
  switching evidence, and monitoring priorities.

### Commercial And Measurement Layer

- `offers-pricing-and-packaging.md`: offers, packages, prices, terms, trials,
  discounts, guarantees, conversion actions, commercial boundaries, and
  effective dates.
- `goals-metrics-and-funnel.md`: goals, funnel definitions, conversion events,
  acquisition baselines, activation, retention, revenue, attribution, tracking
  gaps, and guardrails.
- `campaign-history.md`: prior campaign hypotheses, audiences, offers, assets,
  spend, baselines, tracking, results, confidence, decisions, and reusable
  learnings.

### Brand And Production Layer

- `brand-voice.md`: voice constants, tone flexes, terminology, mechanics,
  messaging pillars, examples, edge cases, confidence, and open questions.
- `anti-ai-writing-rules.md`: generic AI-writing tells and revision checks.
- `visual-identity-and-assets.md`: logos, colours, typography, imagery,
  screenshots, channel specifications, asset locations, rights, and
  restrictions.
- `channel-rules.md`: purpose, audience, funnel stage, identity, formats,
  cadence, CTA, links, offers, proof, voice flex, compliance, capacity,
  approval, and baselines per channel.
- `marketing-operations.md`: team, ownership, budget, systems, access state,
  channel state, production capacity, current priorities, and constraints.

### Evidence And Governance Layer

- `proof-points.md`: the only approval ledger for public-facing claims.
- `case-studies.md`: source-backed customer stories with permissions,
  retrieval tags, proof-point references, and claim limits.
- `qa-policy.md`: output states, severity, blocking checks, approval matrix,
  publication rules, escalation, and post-publication correction.
- `open-questions.md`: unresolved questions, affected decisions, needed
  evidence, owner, next action, and status.
- `changelog.md`: approved changes to canonical context.
- `INDEX.md`: read protocol, task routing, file status, claim rules, and
  publishing rules.
- `../shared/context-read-protocol.md`: shared downstream read contract that
  `INDEX.md` points agents toward.

## Cross-File Rules

1. Store a fact once in its canonical file and link to it elsewhere.
2. Reference sources with stable IDs; do not paste unsupported facts into
   canonical context.
3. Keep observed public messaging in `public-asset-audit.md` until promoted.
4. Keep customer verbatims in `customer-research-and-voc.md`; public use also
   requires recorded permission and, where it becomes a claim, an approved
   proof point.
5. Keep current product capabilities separate from roadmap items.
6. Keep current prices and offers effective-dated. Retire old terms instead of
   silently overwriting history.
7. Keep performance baselines in `goals-metrics-and-funnel.md`; keep individual
   campaign evidence and decisions in `campaign-history.md`.
8. Keep passwords, tokens, credentials, personal data, and other secrets out of
   `.agent-context/`.
9. Route every unresolved contradiction or missing approval to
   `open-questions.md`.
10. If raw sources remain outside `.agent-context/inbox/`, record the source
    pool path, owner, readable scope, confidentiality, and limitations in
    `sources.md` and `INDEX.md`.
11. Show source-level public capture before presenting a confident public audit
    summary. If capture is partial, state the limitation in the readout.
12. When a user gives explicit approval, update the relevant file status,
    approver, scope, date, and changelog entry immediately.
13. If a chat attachment is used as evidence, record enough durable information
    for a future agent to find or understand it without relying on chat memory.

## Completion Levels

- `Not started`: template exists but no meaningful source-backed content.
- `Draft`: content exists but important fields or approvals remain open.
- `Usable with limitations`: enough approved context for named tasks; limits
  are recorded in `INDEX.md`.
- `Approved`: owner has approved the file for its defined scope.
- `Review due`: previously usable context may now be stale.

Stage 1 does not require every optional field to be known. It requires unknowns
to be visible and prevents agents from treating absence as permission.
