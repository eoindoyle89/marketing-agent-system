# Staged Interview Guide

Use this reference after the public audit, private-source review, contradiction
report, and source map. Ask two to five targeted questions at a time. Skip
questions already answered by sources. Summarize each stage and ask the user to
correct it before drafting the relevant files.

If the user approves a staged output, file, section, claim, or policy, stop and
record that approval before continuing. Update status metadata, approver, scope,
date, relevant source or claim rows, and `changelog.md`. Approval is not
complete while it only exists in chat.

## Stage A: Company, Product, And Operating Context

Write to `company-context.md`, `product-capabilities-and-funnel.md`, and
`marketing-operations.md`.

Cover:

- company identity, portfolio, markets, stage, business model, and GTM motion;
- current products or services, users, buyers, capabilities, limitations,
  integrations, delivery model, and roadmap boundaries;
- customer journey, first value, activation, retention behaviours, and known
  friction;
- team ownership, budget, systems, channel state, production capacity,
  priorities, deadlines, and constraints.

Ask for sources or mark unknown:

- Which capabilities are current, beta, planned, or retired?
- What can marketing never imply about the product?
- Who owns each marketing area and who can approve work?
- Which systems are authoritative for customer, product, campaign, and revenue
  data?

## Stage B: Customer Research, ICP, And Positioning

Write to `customer-research-and-voc.md` and `positioning-and-icp.md`.

Cover:

- research scope, date range, sample, segments, and bias;
- functional, emotional, and social jobs;
- pains, trigger events, desired outcomes, objections, alternatives, and exact
  customer language;
- primary and secondary ICP, exclusions, buying roles, use cases, awareness,
  category, differentiation, switching dynamics, and cost of inaction.

Rules:

- Do not invent personas.
- Treat a persona based on fewer than five independent data points as
  provisional.
- Preserve exact quotes, source IDs, context, segment, and permission.
- Distinguish what customers say from what the company wants to say.

## Stage C: Competitive Context

Write to `competitive-context.md` and link summaries from
`positioning-and-icp.md`.

Cover:

- direct competitors, secondary approaches, indirect alternatives, and doing
  nothing;
- competitor target audience, positioning, capabilities, pricing, proof,
  strengths, and weaknesses;
- where the company is stronger, where competitors are stronger, switching
  evidence, migration support, threats, and monitoring priorities.

Do not turn inferred competitor weaknesses into public claims. Competitive
claims must also be approved in `proof-points.md`.

## Stage D: Offers, Pricing, Goals, And Measurement

Write to `offers-pricing-and-packaging.md` and
`goals-metrics-and-funnel.md`.

Cover:

- current offers, packages, prices, billing, value metric, trials, discounts,
  bonuses, guarantees, eligibility, dates, and commercial boundaries;
- primary conversion actions by journey stage;
- business goals, baselines, targets, deadlines, funnel definitions,
  conversion events, acquisition economics, activation, retention, revenue,
  attribution, reporting period, tracking gaps, and guardrails.

Require effective dates and source IDs. Never fill a missing baseline with an
industry benchmark and present it as company performance.

## Stage E: Brand Voice, Writing, And Visual Identity

Write to `brand-voice.md`, `anti-ai-writing-rules.md`, and
`visual-identity-and-assets.md`.

Cover:

- positioning anchor, audience, voice attributes, tone flexes, do/don't
  rewrites, terminology, grammar, messaging pillars, formatting, examples,
  edge cases, confidence, and open questions;
- generic AI-writing tells versus company-specific banned terms;
- approved logos, colours, typography, imagery, motion, screenshots, channel
  specifications, asset locations, licences, permissions, and forbidden uses.

Do not infer visual rules from a website alone. Record them as observed until
the user confirms or supplies guidelines.

## Stage F: Proof Points And Case Studies

Write to `proof-points.md` and `case-studies.md`.

For every proof point capture:

- claim type, exact claim, audience or use case, source IDs, evidence period,
  sample or calculation, status, allowed wording, forbidden overclaim,
  approver, review date, permissions, and channel restrictions.

For every case study capture:

- customer profile, permission, industry, size, personas, use case, product
  capabilities, situation, constraint, action, implementation period, result,
  proof-point IDs, quote, reusable angles, retrieval tags, and prohibited
  claims.

No customer name, logo, quote, or result becomes public merely because it
appears in an internal deck.

## Stage G: Channels And Campaign History

Write to `channel-rules.md` and `campaign-history.md`.

Configure only relevant channels. For each one cover:

- purpose, audience, funnel stage, account identity, formats, specifications,
  cadence, CTA, link and UTM rules, offer and proof restrictions, voice flex,
  mandatory elements, accessibility, compliance, capacity, approver, and
  performance baseline.

For prior campaigns capture:

- hypothesis, audience, offer, channels, assets, landing page, dates, spend,
  tracking, attribution window, baseline, KPI, result, confidence,
  limitations, decision, follow-up, and reusable assets.

Separate “did not work” from “not measured well enough to know.”

## Stage H: QA, Approval, And Escalation

Write to `qa-policy.md`, `open-questions.md`, `INDEX.md`, and `changelog.md`.

Cover:

- draft, reviewed, approved, published/sent, and retired states;
- blocker, major, and minor failures;
- factual, positioning, voice, offer, channel, legal/privacy, asset-rights,
  accessibility, and tracking checks;
- reviewers and approvers by output or risk class;
- approval scope, record location, external-action owner, monitoring,
  correction, takedown, and escalation authority.

Confirm that approval for one asset, version, channel, or campaign does not
create blanket approval for future use.

## Stage Completion Report

After each stage report:

```text
Stage:
Files drafted or updated:
Sources used:
Confirmed:
Unverified:
Contradictions:
Approvals needed:
Approvals recorded:
Ready for user review:
```
