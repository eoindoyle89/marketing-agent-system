# Agent Context Index

## Metadata

- Owner:
- Status: Draft
- Last updated:
- Review cadence:

## Purpose

This folder is the source of truth for marketing agents working on this company.
Agents must read this index before reading task-specific context files.

## Store

- Store mode: `Unconfigured`
- GitHub repo: `Unconfigured`
- Local path: `Unconfigured`
- Accepted source pools: `Unconfigured`
- Shared read protocol: `shared/context-read-protocol.md v0.1`
- Last updated: `Unconfigured`

## Read Protocol

Downstream agents must follow the shared context-read protocol:
`shared/context-read-protocol.md v0.1`.

Minimum run sequence:

1. Read this index first.
2. Classify the request into one primary task family.
3. Read all core files.
4. Read all `Required` files for the selected task family.
5. Read `Conditional` files only when the request triggers them.
6. Build a task-local context ledger before producing output.
7. Check file status, proof-point status, source permission, freshness, and
   contradictions.
8. Ask only for task-specific information that materially blocks the task.
9. Produce only inside approved context boundaries.
10. End substantive outputs with a short context note covering files used,
    limits, needed updates, and approval requirements.

Universal boundaries:

- Treat canonical context files as company truth only inside their stated
  status, effective date, confidence, and approval boundaries.
- Use `sources.md` and `public-asset-audit.md` for provenance and observed
  public messaging, not as automatic approval.
- When context conflicts, prefer the current approved source with the clearest
  authority. Record unresolved conflicts in `open-questions.md`; do not choose
  silently.
- Do not use stale, unverified, contradicted, retired, restricted, or
  out-of-scope information in public-facing output.
- Raw sources may live in `.agent-context/inbox/`, an Obsidian vault, a local
  folder, a synced drive export, a system export, chat attachments, or
  individual files. Read only source pools explicitly recorded in `sources.md`
  or explicitly approved in the current task.
- When a user explicitly approves a file, section, claim, or scoped output,
  update the relevant status, approver, scope, date, and `changelog.md`
  immediately before continuing.

Context ledger:

```text
Context path:
Index status:
Task family:
Core files read:
Required files read:
Conditional files read:
Approved claims available:
Use-with-boundary claims available:
Restricted or stale inputs excluded:
Contradictions affecting this task:
Missing inputs that block the task:
Missing inputs that do not block the task:
```

## Core Reads

All marketing strategy and production agents read:

- `company-context.md`
- `positioning-and-icp.md`
- `brand-voice.md`
- `qa-policy.md`

All external-facing drafting agents also read:

- `anti-ai-writing-rules.md`
- `proof-points.md`
- `channel-rules.md`

## Required Reads By Task

| Task family | Required beyond core | Conditional reads |
|---|---|---|
| Product marketing, positioning, personas | `product-capabilities-and-funnel.md`, `customer-research-and-voc.md`, `competitive-context.md` | `offers-pricing-and-packaging.md`, `proof-points.md` |
| Content strategy, copy, social, email, PR | `customer-research-and-voc.md`, `channel-rules.md`, `proof-points.md` | `case-studies.md`, `campaign-history.md`, `public-asset-audit.md`, `visual-identity-and-assets.md` |
| Ads and creative | `offers-pricing-and-packaging.md`, `goals-metrics-and-funnel.md`, `campaign-history.md`, `marketing-operations.md`, `visual-identity-and-assets.md` | `customer-research-and-voc.md`, `case-studies.md` |
| SEO, AI search, site architecture, app stores | `public-asset-audit.md`, `goals-metrics-and-funnel.md`, `product-capabilities-and-funnel.md` | `competitive-context.md`, `marketing-operations.md`, `case-studies.md` |
| CRO, signup, onboarding, paywalls, churn | `product-capabilities-and-funnel.md`, `goals-metrics-and-funnel.md`, `offers-pricing-and-packaging.md` | `customer-research-and-voc.md`, `campaign-history.md`, `marketing-operations.md` |
| Pricing, offers, launch, partnerships, referrals | `offers-pricing-and-packaging.md`, `competitive-context.md`, `goals-metrics-and-funnel.md`, `marketing-operations.md` | `customer-research-and-voc.md`, `campaign-history.md`, `case-studies.md` |
| Sales enablement, outbound, prospecting, RevOps | `positioning-and-icp.md`, `proof-points.md`, `case-studies.md`, `offers-pricing-and-packaging.md` | `competitive-context.md`, `customer-research-and-voc.md`, `goals-metrics-and-funnel.md`, `marketing-operations.md` |
| Analytics, experiments, campaign planning | `goals-metrics-and-funnel.md`, `campaign-history.md`, `marketing-operations.md` | `channel-rules.md`, `offers-pricing-and-packaging.md` |
| Image and video production | `visual-identity-and-assets.md`, `channel-rules.md`, `qa-policy.md` | `product-capabilities-and-funnel.md`, `proof-points.md` |

## Context File Status

| File | Owner | Status | Last updated | Review due |
|---|---|---|---|---|
| `company-context.md` |  | Draft |  |  |
| `positioning-and-icp.md` |  | Draft |  |  |
| `customer-research-and-voc.md` |  | Draft |  |  |
| `competitive-context.md` |  | Draft |  |  |
| `product-capabilities-and-funnel.md` |  | Draft |  |  |
| `offers-pricing-and-packaging.md` |  | Draft |  |  |
| `goals-metrics-and-funnel.md` |  | Draft |  |  |
| `marketing-operations.md` |  | Draft |  |  |
| `brand-voice.md` |  | Draft |  |  |
| `visual-identity-and-assets.md` |  | Draft |  |  |
| `proof-points.md` |  | Draft |  |  |
| `case-studies.md` |  | Draft |  |  |
| `channel-rules.md` |  | Draft |  |  |
| `campaign-history.md` |  | Draft |  |  |
| `qa-policy.md` |  | Draft |  |  |

## Claim Rules

- Use only claims marked `Approved` or `Use With Boundary`.
- Preserve the boundary for every `Use With Boundary` claim.
- Do not use `Unverified`, `Contradicted`, or `Retired` claims in public-facing copy.
- If a needed fact is missing, add it to `open-questions.md`.

## Publishing Rules

Agents may draft and review. They may not publish, send, submit, or externally
act without explicit human approval.
