# Agent Context Index — Quietude (Example)

> **This is a worked example with fictional data.** Quietude is the fictional
> company used across this repo's examples. Structure follows
> `templates/agent-context/INDEX.md`; content is illustrative and abridged.

## Metadata

- Owner: Casey (fCMO)
- Status: Active
- Last updated: 2026-06-30
- Review cadence: Monthly

## Store

- Store mode: Private GitHub repo + local clone
- GitHub repo: `quietude/quietude-marketing-context` (private, fictional)
- Local path: `~/company-context/quietude-marketing-context`
- Accepted source pools: `.agent-context/inbox/`, founder Notion export,
  Customer.io and App Store exports, chat attachments (indexed per source)
- Shared read protocol: `shared/context-read-protocol.md v0.1`
- Last updated: 2026-06-30

## Read Protocol

Downstream agents follow `shared/context-read-protocol.md v0.1`: read this
index first, classify the request into one task family, read core files, then
required and conditional files for that family, build a context ledger, check
claim/status/source boundaries, and end substantive outputs with a compact
context note.

## Core Reads

All marketing strategy and production agents read: `company-context.md`,
`positioning-and-icp.md`, `brand-voice.md`, `qa-policy.md`.

All external-facing drafting agents also read: `anti-ai-writing-rules.md`,
`proof-points.md`, `channel-rules.md`.

## Required Reads By Task

The task-family table matches the repo template. Quietude-specific notes:

| Task family | Quietude notes |
|---|---|
| Content strategy, copy, social, email, PR | Voice rules are strict (see `brand-voice.md`); the meditation-vs-regulation frame leads all content. |
| CRO, signup, onboarding, paywalls, churn | Activation work centers on the first-session experience; see `product-capabilities-and-funnel.md`. |
| Ads and creative | Paid is OFF until the seed closes (`marketing-operations.md`). Planning only. |
| Analytics, experiments, campaign planning | Funnel definitions and baselines in `goals-metrics-and-funnel.md`; do not invent numbers. |

## Context File Status

| File | Owner | Status | Last updated | Review due |
|---|---|---|---|---|
| `sources.md` | Casey | Approved | 2026-06-30 | 2026-07-31 |
| `public-asset-audit.md` | Casey | Approved | 2026-06-12 | 2026-08-12 |
| `company-context.md` | Alex | Approved | 2026-06-14 | 2026-09-14 |
| `positioning-and-icp.md` | Alex | Approved | 2026-06-14 | 2026-09-14 |
| `customer-research-and-voc.md` | Casey | Usable with limitations | 2026-06-18 | 2026-08-18 |
| `competitive-context.md` | Casey | Draft | 2026-06-18 | 2026-07-18 |
| `product-capabilities-and-funnel.md` | Sam | Approved | 2026-06-20 | 2026-08-20 |
| `offers-pricing-and-packaging.md` | Alex | Approved | 2026-06-20 | 2026-09-20 |
| `goals-metrics-and-funnel.md` | Casey | Approved | 2026-06-22 | 2026-07-22 |
| `marketing-operations.md` | Casey | Approved | 2026-06-22 | 2026-09-22 |
| `brand-voice.md` | Alex | Approved | 2026-06-16 | 2026-09-16 |
| `anti-ai-writing-rules.md` | Casey | Approved | 2026-06-16 | 2026-12-16 |
| `visual-identity-and-assets.md` | Devon | Draft | 2026-06-24 | 2026-07-24 |
| `proof-points.md` | Alex | Approved | 2026-06-26 | 2026-07-26 |
| `case-studies.md` | Casey | Draft | 2026-06-26 | 2026-08-26 |
| `channel-rules.md` | Casey | Approved | 2026-06-28 | 2026-09-28 |
| `campaign-history.md` | Casey | Usable with limitations | 2026-06-28 | 2026-09-28 |
| `qa-policy.md` | Alex | Approved | 2026-06-28 | 2026-12-28 |
| `open-questions.md` | Casey | Active | 2026-06-30 | Weekly |
| `changelog.md` | Casey | Active | 2026-06-30 | — |

## Claim Rules

Use only claims marked `Approved` or `Use With Boundary` in
`proof-points.md`, preserving every recorded boundary. Missing facts go to
`open-questions.md`, never into copy.

## Publishing Rules

Agents draft and review. They do not publish, send, submit, spend, or
externally act without explicit human approval from Alex or Casey.
