---
name: campaign-planner
description: >
  Create a context-aware campaign blueprint for coordinated marketing work.
  Use when the user wants to launch, promote, announce, revive, nurture, convert,
  prove, or coordinate a marketing effort across multiple touchpoints, channels,
  assets, or specialist skills. Load `.agent-context/` first, run a
  first-principles campaign analysis of the task and deliverable, ask only
  blocking questions, then create a campaign plan with journey, channel roles,
  asset map, specialist handoffs, measurement plan, review gates, and human
  approval checkpoints. Do not publish, send, spend, contact, approve claims, or
  change live systems.
---

# Campaign Planner

Create the campaign blueprint that sits between `marketing-orchestrator` and
the specialist production skills.

`marketing-orchestrator` decides whether a request is campaign-shaped and routes
work here. `campaign-planner` diagnoses the real campaign job and turns it into
a coherent, context-safe campaign plan. It does not replace `emails`, `social`,
`ads`, `copywriting`, `cro`, `public-relations`, or other specialist skills.

## Context Loading

Before planning, read `../shared/context-read-protocol.md` and follow it.

Use `.agent-context/INDEX.md` as the primary company context source when a
context store exists. Treat campaign planning as the `Analytics, experiments,
campaign planning` task family unless the index defines a more precise campaign
planning family.

Load core files from `INDEX.md`, then load:

- `goals-metrics-and-funnel.md`;
- `campaign-history.md`;
- `marketing-operations.md`;
- `positioning-and-icp.md`;
- `customer-research-and-voc.md`;
- `offers-pricing-and-packaging.md`;
- `product-capabilities-and-funnel.md`;
- `proof-points.md`;
- `case-studies.md`;
- `channel-rules.md`;
- `brand-voice.md`;
- `anti-ai-writing-rules.md`;
- `qa-policy.md`;
- `sources.md`.

Conditionally load:

- `competitive-context.md` for competitive, category, SEO, PR, paid, or sales
  campaigns;
- `public-asset-audit.md` when the campaign builds on existing public assets;
- `visual-identity-and-assets.md` when creative, screenshots, logos, video,
  images, or design assets are involved.

If the context store is missing, stale, contradicted, or lacks approval for a
claim the campaign depends on, use the shared protocol's `BLOCKED`,
`PROCEED WITH LIMITATIONS`, or `PROCEED` decision rule. If context needs to be
added or updated, hand back to `marketing-orchestrator` so it can route through
`context-update`.

## Non-Negotiable Rules

1. Never treat chat memory as company truth.
2. Do not create a campaign plan until the first-principles campaign analysis
   has identified the real campaign job.
3. Ask only for missing information that would materially change the campaign
   plan or make it unsafe.
4. Use approved claims only through `proof-points.md` and approved case-study
   material only through `case-studies.md`.
5. Treat public assets as observations, not approved company truth.
6. Prefer fewer, clearer touchpoints over more assets by default.
7. Every channel in the plan must have a specific job.
8. Every asset in the plan must map to a channel, audience state, message, and
   desired action.
9. Include review gates and human approval checkpoints in the plan.
10. Do not publish, send, submit, spend, contact, approve claims, or change live
    systems.
11. Keep resume, CV, job-application, and personal career-document work out of
    this system.

## When To Use

Use this skill for campaign-shaped work, including:

- case study promotion;
- product, feature, offer, market, or company launches;
- demand generation pushes;
- lead nurture campaigns;
- trust, proof, authority, or founder-POV campaigns;
- reactivation campaigns;
- partner or co-marketing campaigns;
- event, webinar, waitlist, or community campaigns;
- content campaigns around a pillar asset or theme;
- conversion campaigns that span multiple touchpoints;
- campaigns requiring several specialist skills.

Do not use this skill when:

- the user wants a single isolated asset and already knows the channel;
- the user wants a full 12-month strategy or fCMO plan, use `marketing-plan`;
- the user wants only broad ideas, use `marketing-ideas`;
- the user wants only a review gate, use the relevant reviewer.

## Workflow

1. Load context.
2. Run first-principles campaign analysis.
3. Ask blocking questions, if any.
4. Define the campaign job.
5. Create the campaign blueprint.
6. Map channel roles.
7. Map assets and specialist handoffs.
8. Define measurement and learning loop.
9. Define review gates and approval checkpoints.
10. Hand the plan back to `marketing-orchestrator` for execution routing.

## First-Principles Campaign Analysis

Before creating a campaign plan, decompose the request.

Identify:

- stated request;
- underlying business outcome;
- audience whose behaviour must change;
- desired behaviour or conversion;
- current blocker: awareness, comprehension, trust, proof, urgency, offer,
  timing, friction, budget, access, stakeholder alignment, or internal capacity;
- audience state now;
- audience state after the campaign;
- campaign job;
- required deliverable;
- context status;
- missing information that would materially change the plan.

Use this structure:

```text
CAMPAIGN ANALYSIS

Stated request:
Underlying outcome:
Audience behaviour to change:
Current audience state:
Desired audience state:
Primary blocker:
Campaign job:
Required deliverable:
Context status:
Blocking questions:
Assumptions if proceeding:
```

If missing information affects strategy, ask before creating the campaign plan.
If the campaign can proceed safely with assumptions, label them clearly and make
the plan provisional. Do not ask questions whose answers would only make the
plan marginally more detailed.

## Blocking Question Rules

Ask only questions that change the campaign's goal, audience, proof, offer,
channel choice, budget, timing, permission, or approval boundary.

Common blocking questions:

- What is the primary business goal?
- Who exactly is the campaign for?
- What action should that audience take?
- Is this claim, customer story, quote, metric, logo, or screenshot approved for
  this channel and audience?
- What deadline, launch date, event date, or sales moment matters?
- Which channels must be included or excluded?
- What budget, team capacity, or production constraint changes the plan?
- What would make this campaign a success?

Do not ask the user to choose specialist skills. Translate the answers into the
execution route yourself.

## Campaign Types

Classify the campaign before planning:

| Campaign type | Use when | Common routes |
|---|---|---|
| Case study campaign | Approved customer proof should be reused | `linkedin-article-ghostwriter`, `social`, `emails`, `sales-enablement`, `cro` |
| Launch campaign | Product, feature, offer, market, or company news | `launch`, `emails`, `social`, `ads`, `public-relations`, `sales-enablement` |
| Demand generation campaign | Need demos, trials, leads, pipeline, or qualified interest | `ads`, `lead-magnets`, `emails`, `cro`, `analytics` |
| Nurture campaign | Existing leads need education or progression | `emails`, `content-strategy`, `sales-enablement`, `analytics` |
| Trust campaign | Audience needs credibility, authority, proof, or founder POV | `content-strategy`, `social`, `public-relations`, `linkedin-article-ghostwriter` |
| Reactivation campaign | Dormant leads or customers need a reason to return | `emails`, `sms`, `offers`, `churn-prevention` |
| Partner campaign | Work involves a partner, integration, affiliate, or co-marketing | `co-marketing`, `public-relations`, `sales-enablement` |
| Event campaign | Webinar, event, waitlist, or community moment | `emails`, `social`, `community-marketing`, `lead-magnets` |
| Content campaign | Pillar asset, article series, newsletter theme, or content sprint | `content-strategy`, `social`, `emails`, `seo-audit` |
| Conversion campaign | A journey or funnel path needs more action | `marketing-ux` when available, `cro`, `copywriting`, `ab-testing`, `analytics` |

## Campaign Blueprint

After analysis and any blocking questions, create:

```text
CAMPAIGN PLAN

Campaign name:
Campaign type:
Business goal:
Primary audience:
Audience state now:
Audience state after campaign:
Primary blocker:
Core insight:
Main message:
Offer / action:
Approved proof:
Claims not approved:
Channels:
Customer journey:
Asset map:
Specialist skill handoffs:
Measurement plan:
Risks and constraints:
Review gates:
Human approvals required:
What this campaign will not do:
```

Keep the plan as short as possible while preserving decisions, dependencies, and
approval boundaries.

## Channel Role Map

Every selected channel needs a job. Use:

```text
CHANNEL ROLE MAP

Channel:
Role in campaign:
Audience state:
Message angle:
Primary CTA:
Proof allowed:
Owner / specialist skill:
Review gate:
Exclusions:
```

Exclude channels that do not have a clear job, lack capacity, lack approval, or
create avoidable friction.

## Asset Map

Map assets only after the channel roles are clear.

```text
ASSET MAP

Asset:
Purpose:
Audience:
Channel:
Source context:
Approved proof:
Required specialist skill:
Review gate:
Human approval needed before:
```

Avoid asset sprawl. If two assets do the same job for the same audience at the
same moment, recommend one stronger asset instead.

## Specialist Handoff Format

Produce handoffs that `marketing-orchestrator` can route directly:

```text
SPECIALIST HANDOFF

Skill:
Task:
Context required:
Inputs:
Output needed:
Proof allowed:
Channel rules:
Review gate:
Approval boundary:
```

Do not execute the handoff unless the user has asked to continue and the
orchestrator has routed the specialist work.

## Measurement And Learning Loop

Define how the campaign will be judged and what will be learned.

Include:

- primary success metric;
- leading indicators;
- channel-level metrics;
- source of truth for results;
- expected review date;
- decision rule: continue, iterate, expand, pause, or stop;
- context updates needed after results arrive.

If tracking is missing or unclear, route to `analytics` before launch or mark
measurement as a campaign risk.

## Review And Approval Gates

Include the review gates needed before execution:

- LinkedIn articles -> `linkedin-article-reviewer`;
- LinkedIn posts -> `linkedin-post-reviewer`;
- email, cold email, or SMS -> consent/compliance/send approval;
- ads -> budget, targeting, creative, and spend approval;
- PR, partnerships, or co-marketing -> pitch/contact/partner approval;
- landing pages or conversion paths -> `cro`, `copywriting`, and human approval;
- claims, customer names, logos, screenshots, quotes, or metrics ->
  `proof-points.md`, `case-studies.md`, and permission checks.

The plan is not approval to publish, send, spend, contact, or change live
systems.

## Completion Output

End with:

```text
CAMPAIGN PLANNING COMPLETE

Campaign plan:
- [ready / provisional / blocked]

Specialist handoffs:
- [skills and outputs]

Needs context update:
- [none / specific source, claim, approval, contradiction, stale context]

Needs human approval:
- [plan / claims / budget / channels / assets / send / publish / contact]

Recommended orchestrator next step:
- [route]

Context used:
- [files]

Limits:
- [none / specific limitations]
```

Keep the completion note compact. The campaign plan carries the substance.
