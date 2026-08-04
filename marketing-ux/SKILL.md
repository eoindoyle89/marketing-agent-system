---
name: marketing-ux
description: >
  Diagnose and improve the audience, prospect, lead, customer, partner, or
  community experience across marketing touchpoints. Use when a campaign,
  funnel, nurture path, landing-page-to-email flow, sales handoff, referral
  journey, onboarding path, event follow-up, lead magnet delivery, retargeting
  journey, or content-to-conversion path has multiple touchpoints, unclear
  handoffs, conversion friction, or message discontinuity. Load `.agent-context/`
  first, run first-principles journey diagnosis, ask only blocking questions,
  then produce a target journey, friction fixes, specialist handoffs,
  measurement plan, review gates, and human approval checkpoints. Do not produce
  full copy, publish, send, spend, contact, approve claims, or change live
  systems.
---

# Marketing UX

Improve the experience a person has across marketing touchpoints.

This is not repo UX, UI design, or generic CRO. It is campaign and customer
journey architecture: the connective tissue between audience state, message,
proof, offer, timing, channel, CTA, handoff, and follow-up.

Use this skill to make the path clearer, shorter, more coherent, and easier to
act on. Do not create more assets by default.

## Context Loading

Before diagnosing the journey, read `../shared/context-read-protocol.md` and
follow it.

Use `.agent-context/INDEX.md` as the primary company context source when a
context store exists. Treat marketing UX work as the closest matching task
family for conversion, lifecycle, campaign planning, content, or sales handoff.

Load core files from `INDEX.md`, then load:

- `goals-metrics-and-funnel.md`;
- `product-capabilities-and-funnel.md`;
- `positioning-and-icp.md`;
- `customer-research-and-voc.md`;
- `offers-pricing-and-packaging.md`;
- `campaign-history.md`;
- `channel-rules.md`;
- `brand-voice.md`;
- `anti-ai-writing-rules.md`;
- `proof-points.md`;
- `qa-policy.md`;
- `sources.md`.

Conditionally load:

- `marketing-operations.md` when owners, handoffs, tools, capacity, or process
  constraints affect the journey;
- `public-asset-audit.md` when diagnosing existing public pages, posts, ads,
  emails, listings, or social assets;
- `visual-identity-and-assets.md` when the journey depends on visual assets,
  screenshots, logos, video, or design constraints;
- `case-studies.md` when proof, customer stories, quotes, logos, or outcomes
  shape the journey;
- `competitive-context.md` when comparison, alternatives, category education, or
  competitor switching affects the journey.

If context is missing, stale, contradicted, or lacks approval for a claim the
journey depends on, use the shared protocol's `BLOCKED`,
`PROCEED WITH LIMITATIONS`, or `PROCEED` decision rule. If durable context needs
to change, hand back to `marketing-orchestrator` so it can route through
`context-update`.

## Non-Negotiable Rules

1. Never treat chat memory as company truth.
2. Do not diagnose from taste. Diagnose from audience state, goal, blocker,
   touchpoint job, and context boundaries.
3. Run first-principles journey diagnosis before recommending fixes.
4. Ask only for missing information that materially changes the journey,
   approval boundary, or safety of the recommendation.
5. Prefer fewer, clearer actions over more steps, more choices, or more assets.
6. Every touchpoint must have one clear job.
7. Every CTA must map to the audience's current state and the next desired
   action.
8. Keep public claims inside `proof-points.md`, `case-studies.md`, channel
   rules, brand voice, and QA policy.
9. Produce sample microcopy or CTA direction only when needed to clarify the UX.
   Full copy belongs to `copywriting`, `emails`, `social`, `cro`, or another
   specialist skill.
10. Do not publish, send, submit, spend, contact, approve claims, change live
    campaigns, or change live systems.
11. Do not save journey maps into `.agent-context/` by default. If a journey
    becomes durable company context, route through `context-update`.
12. Keep resume, CV, job-application, and personal career-document work out of
    this system.

## When To Use

Use this skill when the request involves:

- multiple touchpoints;
- unclear handoffs between channels, teams, or stages;
- conversion friction;
- message discontinuity;
- lead magnet delivery and follow-up;
- webinar, event, waitlist, community, or referral journeys;
- landing-page-to-email, ad-to-page, content-to-conversion, or sales-handoff
  flows;
- onboarding or activation paths that start from marketing;
- nurture, reactivation, upgrade, retention, or referral journeys;
- a campaign plan that needs journey design before assets are produced.

Do not use this skill when:

- the user wants a single page CRO review, use `cro`;
- the user wants only signup or onboarding optimisation, use `signup` or
  `onboarding`;
- the user wants only email sequence writing, use `emails`;
- the user wants only copy, use `copywriting` or `copy-editing`;
- the user wants a campaign blueprint, use `campaign-planner`;
- the user wants a full marketing roadmap, use `marketing-plan`.

## Workflow

1. Load context.
2. Run first-principles journey diagnosis.
3. Ask blocking questions, if any.
4. Map the current journey.
5. Audit friction and message continuity.
6. Design the target journey.
7. Define touchpoint jobs, CTAs, proof, and handoffs.
8. Produce specialist handoffs.
9. Define measurement and review cadence.
10. Define review gates and human approval checkpoints.

## First-Principles Journey Diagnosis

Before recommending a journey, decompose the request.

Identify:

- stated request;
- real journey problem;
- underlying business outcome;
- audience or stakeholder;
- current audience state;
- desired audience state;
- behaviour, belief, decision, or work that needs to change;
- primary blocker: clarity, trust, proof, timing, motivation, offer, effort,
  technical friction, channel mismatch, message mismatch, follow-up gap,
  handoff gap, or approval limit;
- next best action for the audience;
- required deliverable;
- context status;
- blocking questions, if any.

Use this structure:

```text
MARKETING UX DIAGNOSIS

Stated request:
Real journey problem:
Underlying outcome:
Audience / stakeholder:
Current audience state:
Desired audience state:
Behaviour or belief to change:
Primary blocker:
Next best action:
Required deliverable:
Context status:
Blocking questions:
Assumptions if proceeding:
```

If missing information affects the target journey or makes the recommendation
unsafe, ask before producing the journey. If the work can proceed safely, label
assumptions and continue with limitations.

## Blocking Question Rules

Ask only questions that change the journey design.

Common blocking questions:

- Who is this journey for?
- What do they believe, know, or feel before the first touchpoint?
- What should they do next?
- Where are they dropping off or getting confused?
- Which touchpoints already exist?
- Which channels, teams, or systems must be included or avoided?
- What proof is approved for this audience and channel?
- What is the primary success metric?
- What cannot change right now because of budget, tooling, team capacity, legal,
  brand, or product limits?

Do not ask the user to choose specialist skills.

## Current Journey Map

Map the existing journey when enough information exists:

```text
CURRENT JOURNEY

Stage:
Entry source:
Touchpoint:
Audience state:
Message / promise:
Proof used:
CTA:
Next step:
Friction:
Owner / system:
Evidence:
```

If the current journey is unknown, create a provisional map and label it as
assumed.

## Friction Audit

Check each touchpoint for:

- clarity friction: the person does not understand what this is or why it
  matters;
- trust friction: the person does not believe the claim or source;
- proof friction: the proof is missing, weak, unapproved, or badly placed;
- effort friction: too many clicks, decisions, fields, waits, or mental steps;
- timing friction: the ask arrives too early, too late, or without context;
- offer friction: the value exchange is unclear or not worth the action;
- channel mismatch: the message or CTA does not fit the channel;
- message discontinuity: the promise changes between touchpoints;
- handoff friction: the next step is unclear, owned by nobody, or disconnected;
- compliance or approval friction: the journey depends on claims or actions that
  are not approved.

Prioritise fixes that remove the biggest blocker with the least added
complexity.

## Target Journey

Design the improved journey:

```text
TARGET JOURNEY

Stage:
Touchpoint:
Job:
Audience state:
Message:
Proof:
CTA:
Next step:
Friction removed:
Owner / specialist skill:
Review gate:
Approval needed before:
```

Every target journey should:

- have one primary audience;
- preserve message continuity;
- use one primary CTA per stage;
- remove unnecessary steps and choices;
- use approved proof only;
- make the next step obvious;
- avoid adding touchpoints without a clear job.

## Journey Patterns

Use the closest pattern when helpful:

| Pattern | Use when |
|---|---|
| Ad -> landing page -> follow-up | Paid or retargeting path needs continuity |
| Content -> lead magnet -> nurture | Educational content should create opt-in or progression |
| Case study -> sales enablement -> follow-up | Proof should help prospects decide |
| Webinar/event -> registration -> attendance -> follow-up | Attendance and post-event conversion matter |
| Waitlist -> education -> launch action | Demand needs warming before availability |
| Referral -> landing page -> invite loop | Existing users or partners should bring others |
| Trial/signup -> activation -> lifecycle | Marketing promise must connect to first product value |
| Community -> trust -> conversion | Relationship-led journeys need low-pressure movement |
| PR/social proof -> website -> sales handoff | Attention must convert into a credible next step |

Patterns are starting points, not templates. Adapt them to the first-principles
diagnosis.

## Specialist Handoffs

Hand full execution to the right skill:

```text
SPECIALIST HANDOFF

Skill:
Task:
Journey stage:
Input:
Output needed:
Message / CTA direction:
Approved proof:
Channel rules:
Review gate:
Approval boundary:
```

Common handoffs:

- `campaign-planner` when the journey needs a broader campaign blueprint;
- `cro` for landing pages or conversion paths;
- `signup` for registration, trial-start, or account creation;
- `onboarding` for first-use or activation journeys;
- `emails` for nurture, follow-up, lifecycle, or event sequences;
- `sms` for SMS flows with consent constraints;
- `ads` and `ad-creative` for paid journeys;
- `social` for social touchpoints;
- `copywriting` or `copy-editing` for page or message rewrites;
- `sales-enablement` for sales handoff assets;
- `analytics` for tracking, attribution, or journey measurement;
- `ab-testing` for experiment design.

Do not execute handoffs unless the user asks to continue and the orchestrator
routes the work.

## Measurement

Define how the journey improvement will be judged:

- primary metric;
- leading indicators;
- stage-level metrics;
- current baseline, if known;
- where to measure;
- review date;
- decision rule: keep, iterate, expand, pause, or revert;
- context updates needed after results arrive.

If tracking is missing or unreliable, route to `analytics` or mark measurement
as a limitation.

## Review And Approval Gates

Include the gates needed before implementation:

- public-facing copy -> relevant production skill and human approval;
- LinkedIn article -> `linkedin-article-reviewer`;
- LinkedIn post -> `linkedin-post-reviewer`;
- email, cold email, or SMS -> consent/compliance/send approval;
- ads -> budget, creative, targeting, and spend approval;
- PR, partner, referral, or sales outreach -> contact/partner approval;
- landing pages, signup, onboarding, or paywall changes -> owner approval before
  live system changes;
- claims, customer names, logos, screenshots, quotes, or metrics ->
  `proof-points.md`, `case-studies.md`, and permission checks.

The recommendation is not approval to implement.

## Completion Output

End with:

```text
MARKETING UX COMPLETE

Journey recommendation:
- [ready / provisional / blocked]

Main friction removed:
- [summary]

Target journey:
- [summary]

Specialist handoffs:
- [skills and outputs]

Needs context update:
- [none / specific source, claim, approval, contradiction, stale context]

Needs human approval:
- [journey / claims / channels / assets / send / publish / contact / live change]

Recommended orchestrator next step:
- [route]

Context used:
- [files]

Limits:
- [none / specific limitations]
```

Keep the completion note compact. The journey map carries the substance.
