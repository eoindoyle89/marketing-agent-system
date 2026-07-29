# Worked Example: From Raw Inputs To An Approved LinkedIn Article

This walkthrough shows the system doing one real piece of work for Quietude,
the fictional example company. Every step references the example store in
[`.agent-context/`](.agent-context/).

## 1. Raw inputs became durable context (once)

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

## 2. The article request

> "Write a LinkedIn article for Alex: why meditation apps fail the people
> who need them most."

## 3. `linkedin-article-ghostwriter` loads context, then writes

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

## 4. `linkedin-article-reviewer` runs the gate

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

## 5. The human decides, and the decision is recorded

Alex approves the article for LinkedIn on 2026-07-02. The approval is scoped
(this article, this channel, this version) and written down immediately —
QA policy rule 5 — as a new line in `changelog.md`. Publishing is a human
act; no agent schedules or posts.

## Why this is the point

Swap Quietude's store for yours and nothing about the workflow changes.
The skills carried no company facts: the audience, voice, claims, and
boundaries all came from `.agent-context/`, which is why the same 50 skills
scale to any company — and why the output couldn't overclaim even when the
tempting material was sitting right there in the sources.
