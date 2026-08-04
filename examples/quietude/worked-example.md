# Worked Example: From Raw Inputs To Approved Marketing Work

This walkthrough shows the system doing two pieces of work for Quietude, the
fictional example company:

1. a focused LinkedIn article;
2. an operating-layer campaign flow using `marketing-orchestrator`,
   `context-update`, `campaign-planner`, `marketing-ux`, specialist handoffs,
   review gates, and human approval.

Every step references the example store in [`.agent-context/`](.agent-context/).

## Part 1: A LinkedIn Article

### 1. Raw inputs became durable context (once)

`marketing-system-setup` ran before any production work: it audited
quietude.app and the App Store listing first (`public-asset-audit.md`),
then indexed the seed deck, the clinical study, funnel exports, and nine
customer interviews as sources with authority and permission recorded
(`sources.md`), surfaced a contradiction (the website said "15,000 live
participants", the deck said "over 14,000"), and interviewed the founder in
stages. The output is twenty context files with owners, statuses, and review
dates — see [`.agent-context/INDEX.md`](.agent-context/INDEX.md).

Two governance details matter later:

- The contradiction was resolved into an approved claim with allowed wording:
  PP-004, "More than 14,000 people have experienced Quietude live."
- A tempting claim — "users report falling asleep faster" — stayed
  `Unverified` (PP-005) and is blocked from public copy, with an open
  question (OQ-001) about measuring it.

### 2. The article request

> "Write a LinkedIn article for Alex: why meditation apps fail the people
> who need them most."

### 3. `linkedin-article-ghostwriter` loads context, then writes

The skill reads `.agent-context/INDEX.md`, classifies the task into the
`Content strategy, copy, social, email, PR` family, and builds its ledger:

```text
Context ledger:
- Context path: ~/company-context/quietude-marketing-context/.agent-context
- Index status: Active (2026-06-30)
- Task family: Content strategy, copy, social, email, PR
- Core files read: company-context, positioning-and-icp, brand-voice, qa-policy
- Required files read: customer-research-and-voc, channel-rules,
  proof-points, anti-ai-writing-rules
- Approved claims available: PP-001, PP-003, PP-004
- Use-with-boundary claims available: PP-002 (fact-sheet wording only)
- Restricted or stale inputs excluded: PP-005 (Unverified), PP-006
  (internal only), competitive-context (Draft — no named competitors)
- Contradictions affecting this task: none open
- Missing inputs that block the task: none
```

The configuration that shapes the draft comes from the store, not the skill:
the reader (an overstimulated professional who has already failed at
meditation apps), the lead frame (bottom-up regulation leads; relaxation
never leads), the mechanism term ("nervous system regulation" — explains,
never headlines), Alex's voice, US English, and both banned-word lists.

**The draft (abridged):**

> **Headline:** Meditation apps fail the people who need them most
>
> **Dek:** The stressed brain can't do what those apps ask of it. There's a
> reason the calmest thing you did this week wasn't a practice at all.
>
> The opening tells a concrete story in Alex's voice — a founder lying awake
> rehearsing tomorrow, meditation app open, subscription active, following
> none of it. The thesis lands early: meditation is top-down; it asks the
> mind to command the body, and the prefrontal cortex is exactly what goes
> offline under stress. The body responds before it has to try — that is
> the bottom-up route. Sections walk the argument: why "try harder to relax"
> fails; what entering through the brainstem means; a practical section the
> reader can use tonight (a three-step wind-down that requires no app); the
> skeptic's objection ("isn't this just white noise with better marketing?")
> answered with the peer-reviewed research claim in its approved wording
> (PP-001). No product pitch. The ending sharpens the thesis instead of
> restating it.
>
> Context used: positioning-and-icp, brand-voice, customer-research-and-voc,
> channel-rules, proof-points, anti-ai-writing-rules
> Limits: sleep-latency claim omitted (PP-005 Unverified)
> Needs update: none
> Approval required before: publishing (Alex)

Note what the store prevented: the draft could not use "clinically proven"
(PP-001 boundary), could not cite "15,000" (PP-004 wording), could not
mention falling asleep faster (PP-005 blocked), and could not name
competitors (competitive-context is Draft).

### 4. `linkedin-article-reviewer` runs the gate

The reviewer loads the same context independently and runs its twelve
principles. Abridged verdict:

```text
1  Audience commitment   PASS  Headline+dek speak to the failed-meditator
2  Lead frame            PASS  Regulation leads; relaxation never leads
3  Headline and dek      PASS
4  Thesis discipline     PASS  One thesis, stated early, landed at the end
5  Structure             BORDERLINE  Section 4 heading is a label, not a
                                     step — rewrite suggested and applied
6  Method                PASS  Three-step wind-down is usable tonight
7  Proof discipline      PASS  PP-001 wording exact; PP-005 correctly absent
8  Objection handling    PASS  Strongest objection, answered fairly
9  Author voice          PASS  Territory: founder's own story
10 Mechanism/pitch       PASS  Mechanism in body only; no pitch found
11 Ending                PASS
12 Language/dialect      FAIL  One em dash; "journey" (banned) — quoted,
                                replacements provided and applied

Final call after fixes: Ready for human approval
```

### 5. The human decides, and the decision is recorded

Alex approves the article for LinkedIn on 2026-07-02. The approval is scoped
(this article, this channel, this version) and written down immediately —
QA policy rule 5 — as a new line in `changelog.md`. Publishing is a human
act; no agent schedules or posts.

## Part 2: A New Source Becomes A Campaign

### 1. The user starts with a messy operating-layer request

> "Use marketing-orchestrator. We just published the live-session results
> article. Create a campaign to promote it, but don't overdo the channels."

The user did not choose a skill chain. That is the orchestrator's job.

### 2. `marketing-orchestrator` runs routing analysis

The orchestrator reads the shared context protocol, then `.agent-context/INDEX.md`.
It sees that the request contains both new source material and a campaign-shaped
goal.

```text
ROUTING ANALYSIS

Stated request: promote the new live-session results article.
Real deliverable: context-safe campaign route and campaign brief.
Underlying outcome: turn fresh proof into qualified awareness and sales
  conversation material.
Audience / stakeholder: overstimulated professionals and the founder/sales
  team using the proof.
Primary blocker: new public source must be indexed before it can become
  reusable proof.
Output type: context update -> campaign plan -> possible journey review.
Minimum useful skill chain: context-update -> campaign-planner -> marketing-ux
  if handoffs are unclear -> specialist skills -> review gates.
Review gates: LinkedIn reviewer for article/post assets; proof checks for
  public claims.
Approval gates: claim use, campaign plan, publishing, sending.
Blocking questions: source URL and approval scope.
```

It does not ask the user to choose between `context-update`,
`campaign-planner`, `marketing-ux`, `social`, `emails`, or
`sales-enablement`.

### 3. `context-update` captures the new public source

The article is treated as a public source, not automatic approved truth.
`context-update` asks only the blocking questions:

```text
Before I update context, I need:
- Is this source approved for internal planning, public campaign use, or draft
  only?
- Who approved the source and on what date?
- Which claims from the source are allowed in public copy?
- Are there any customer names, screenshots, or metrics that must not be reused?
```

The user answers:

> "Approved by Alex on 2026-07-08 for LinkedIn, email, and sales follow-up.
> Use the article's live-participant wording only. Do not imply sleep outcomes."

`context-update` previews the affected files:

```text
CONTEXT UPDATE PREVIEW

Update type: New source + proof point boundary
Source IDs to add: SRC-014
Affected files: sources.md, proof-points.md, campaign-history.md, INDEX.md,
  changelog.md
Claims to add, update, or retire:
- Add SRC-014 as a public source.
- Reinforce PP-004 allowed wording.
- Keep PP-005 blocked.
Approval scope: LinkedIn, email, sales follow-up.
Open questions: none.
Will not do:
- Will not draft external content.
- Will not publish, send, submit, spend, contact, or change live systems.
- Will not push unless explicitly approved.
```

After approval, it updates the context store and records the scoped approval in
`changelog.md`.

### 4. `campaign-planner` builds the campaign blueprint

Now the campaign can be planned from approved context.

```text
CAMPAIGN ANALYSIS

Stated request: promote the live-session results article.
Underlying outcome: create qualified interest without turning proof into hype.
Audience behaviour to change: move from "another wellness app" to "this may
  solve the part meditation apps miss."
Current audience state: aware of meditation apps, skeptical after failed use.
Desired audience state: curious enough to read, share, or ask for more.
Primary blocker: trust and category understanding.
Campaign job: proof-led trust campaign.
Required deliverable: small campaign plan with specialist handoffs.
Context status: proceed, PP-004 allowed, PP-005 blocked.
Blocking questions: none.
```

The campaign plan stays deliberately small:

```text
CAMPAIGN PLAN

Campaign name: Proof Without Hype
Campaign type: Trust campaign / case-study-style proof campaign
Business goal: turn approved live-session proof into qualified awareness.
Primary audience: overstimulated professionals who have failed with
  meditation apps.
Main message: the body often needs a bottom-up route before the mind can
  participate.
Offer / action: read the article or ask for the live-session summary.
Approved proof: PP-001 and PP-004 only.
Claims not approved: sleep-latency or outcome-improvement claims.
Channels:
- LinkedIn founder article
- two supporting LinkedIn posts
- one short email to existing waitlist/subscribers
- sales follow-up snippet for warm conversations
What this campaign will not do:
- no paid ads;
- no new landing page;
- no customer-logo use;
- no sleep-outcome claim.
```

The planner hands work back to `marketing-orchestrator` with specialist routes:

```text
SPECIALIST HANDOFFS

- linkedin-article-ghostwriter: founder article using PP-001 and PP-004 only.
- social: two supporting posts, no engagement bait.
- emails: one short proof-led email, send approval required.
- sales-enablement: follow-up snippet, internal use unless separately approved.
- linkedin-article-reviewer and linkedin-post-reviewer: run before approval.
```

### 5. `marketing-ux` checks the journey before assets are produced

Because the campaign has multiple touchpoints, `marketing-orchestrator` routes
through `marketing-ux` before production.

```text
MARKETING UX DIAGNOSIS

Real journey problem: the proof source could send people into disconnected
  article, email, and sales conversations.
Current audience state: interested but skeptical.
Desired audience state: understands the mechanism and has one low-pressure
  next step.
Primary blocker: message discontinuity and proof overreach risk.
Next best action: read the article or request the live-session summary.
Required deliverable: target journey and handoffs.
```

`marketing-ux` removes one proposed touchpoint: a generic nurture sequence. It
would add work without helping the audience take the next step.

```text
TARGET JOURNEY

Stage: Awareness
Touchpoint: Founder LinkedIn article
Job: reframe why meditation apps fail some people
CTA: read the live-session summary
Proof: PP-001 and PP-004 only

Stage: Reinforcement
Touchpoint: two LinkedIn posts
Job: repeat the mechanism and one practical implication
CTA: read the article
Proof: PP-004 only

Stage: Warm follow-up
Touchpoint: email or sales snippet
Job: give already-interested people the proof source
CTA: reply for the summary or ask a question
Proof: PP-001 and PP-004 only
```

Full copy is not written by `marketing-ux`; it creates the handoffs.

### 6. Specialist skills create assets, then review gates run

`marketing-orchestrator` routes each approved handoff:

- `linkedin-article-ghostwriter` writes the long-form article.
- `social` drafts supporting posts.
- `emails` drafts the short email.
- `sales-enablement` drafts the internal follow-up snippet.
- `linkedin-article-reviewer` and `linkedin-post-reviewer` run before the human
  approves any LinkedIn assets.

The agents still do not publish, send, spend, or contact anyone.

### 7. The human approves the plan and assets

The final state is traceable:

```text
ORCHESTRATION COMPLETE

Request type: proof-led campaign from new approved source.
Skills used: context-update, campaign-planner, marketing-ux,
  linkedin-article-ghostwriter, social, emails, sales-enablement,
  linkedin-article-reviewer, linkedin-post-reviewer.
Context used: INDEX.md, sources.md, proof-points.md, case-studies.md,
  brand-voice.md, anti-ai-writing-rules.md, channel-rules.md,
  campaign-history.md, qa-policy.md.
Context updated: SRC-014 added; PP-004 boundary reinforced; PP-005 still
  blocked.
Outputs created: campaign plan, target journey, specialist handoffs, draft
  assets, review notes.
Review status: LinkedIn assets ready for human approval after fixes.
Needs human approval: campaign plan, final copy, publish/send/contact actions.
Not done: no publishing, sending, ad spend, or live-system changes.
```

## Why this is the point

Swap Quietude's store for yours and nothing about the workflow changes.
The skills carried no company facts: the audience, voice, claims, and
boundaries all came from `.agent-context/`, which is why the same skill library
scales to any company — and why the output couldn't overclaim even when the
tempting material was sitting right there in the sources.
