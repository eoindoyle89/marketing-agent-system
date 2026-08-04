# marketing-agent-system

A marketing-agent system: durable company context, setup, update, and
orchestration agents that maintain it, 50 specialist marketing skills that read
it, and QA gates that keep humans in charge of everything public-facing.

The premise: AI chat memory is not company truth. Marketing agents produce
generic or invented output when the facts they need — positioning, audience,
proof, voice, channel rules — live nowhere durable. This repo fixes that with
an architecture, not a prompt.

## How it works

```text
sources (public + private)
        │
        ▼
marketing-system-setup
context-update          ──►  .agent-context/   (private company store)
                                    │
                                    ▼
                         marketing-orchestrator
                                    │
                                    ▼
                     shared/context-read-protocol.md
                                    │
                                    ▼
                    specialist skills (draft / analyse / plan)
                                    │
                                    ▼
                    review gates ──► human approval ──► publish
```

- **`marketing-system-setup`** provisions a private company context store
  (`.agent-context/`, typically a private GitHub repo cloned locally), audits
  public assets first, reads private sources second, presents contradictions,
  interviews the user in stages, and writes source-backed context files with
  claim status and approval metadata. Templates live in
  [`templates/agent-context/`](templates/agent-context/).
- **`context-update`** keeps company context current after setup. It accepts
  new sources in natural forms like URLs, pasted text, attachments, local
  files, folders, exports, or direct user statements, classifies the update,
  previews affected context files and claims, writes approved changes, records
  `changelog.md`, and commits locally after approval.
- **`marketing-orchestrator`** is the default front door for day-to-day
  marketing work. It classifies messy requests, checks `.agent-context/`,
  routes new or stale company truth through `context-update`, selects the
  smallest useful specialist skill chain, sequences review gates, and stops
  before publishing, sending, spending, contacting, claim approval, or live
  system changes.
- **`campaign-planner`** turns campaign-shaped requests into a campaign
  blueprint. It loads approved context, runs first-principles analysis of the
  real campaign job, asks only blocking questions, maps the journey, channels,
  assets, measurement, specialist handoffs, review gates, and human approvals.
- **[`shared/context-read-protocol.md`](shared/context-read-protocol.md)** is
  the contract every downstream skill follows: read `.agent-context/INDEX.md`
  first, classify the task into a family, load only the required context,
  respect claim and approval boundaries, and report limitations.
- **Specialist skills** cover research, strategy, content, search, paid,
  conversion, lifecycle, sales, ops, and creative. Each declares its task
  family and required context reads. None publish, send, spend, or contact
  anyone — they draft and recommend for human approval.
- **Review gates** like `linkedin-post-reviewer` and
  `linkedin-article-reviewer` run named, failable tests against approved
  context before anything reaches a human approver.

## Skill catalog

| Area | Skills |
|---|---|
| Setup & governance | marketing-system-setup, context-update, marketing-orchestrator |
| Campaign orchestration | campaign-planner |
| Foundation & research | customer-research, competitor-profiling, content-strategy, copywriting, copy-editing, social |
| Search & distribution | seo-audit, ai-seo, site-architecture, programmatic-seo, schema, aso, directory-submissions, competitors |
| Paid, conversion & measurement | ads, ad-creative, ab-testing, analytics, cro, signup, onboarding, paywalls, popups |
| Lifecycle, growth & GTM | emails, cold-email, sms, churn-prevention, referrals, co-marketing, community-marketing, launch, lead-magnets, free-tools, offers, pricing |
| Sales, ops, creative & strategy | prospecting, revops, sales-enablement, public-relations, image, video, marketing-ideas, marketing-psychology, marketing-plan, marketing-loops, marketing-council |
| Production & review gates | linkedin-article-ghostwriter, linkedin-post-reviewer, linkedin-article-reviewer |

Packaging status, provenance flags, and per-skill notes are tracked in
[`PACKAGING.md`](PACKAGING.md).

## Example

[`examples/quietude/`](examples/quietude/) is a complete fictional example:
a populated `.agent-context/` store and a
[worked example](examples/quietude/worked-example.md) that follows one
article from raw inputs through the ghostwriter, the review gate, and a
recorded human approval. The reasoning behind the architecture is written up
in [docs/why-durable-context.md](docs/why-durable-context.md).

## Setup

Start with [SETUP.md](SETUP.md), then run the
[`marketing-system-setup`](marketing-system-setup/) skill. You do not need to
know GitHub first; the setup agent walks through every step and offers a
local-only fallback.

## Principles

- Company truth lives in a durable store, never in chat memory.
- Public assets are observations, not approved facts.
- Every public-facing claim has provenance, status, and allowed wording.
- Agents draft, analyse, and recommend; humans approve, publish, and spend.
- Writing-quality rules are durable context, not model taste.

## Who I am

Eoin Doyle — marketer and founder who builds with AI.
[LinkedIn](https://www.linkedin.com/in/eoindoyle/)

## License

[MIT](LICENSE) © Eoin Doyle. Some skills are adapted from Apache-2.0 licensed
skills in Anthropic's Cowork marketing plugin — see
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and
[`LICENSES/`](LICENSES/).
