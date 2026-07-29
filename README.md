# marketing-agent-system

Marketing agents and quality gates for AI-assisted production.

This repo starts with a setup agent and two public, company-configurable
LinkedIn skills:

- `marketing-system-setup` provisions the private company information store,
  creates `.agent-context/`, guides source-pool selection and source
  collection, and builds durable marketing context before any production agents
  run.
- `linkedin-article-ghostwriter` writes long-form founder or expert LinkedIn
  articles from a developed content idea, using approved company context,
  author voice, channel rules, and proof boundaries.
- `linkedin-post-reviewer` reviews short LinkedIn posts before human approval,
  checking audience fit, lead frame, voice, product-pitch drift, hook strength,
  ending quality, banned words, and dialect.

The broader goal is a marketing-agent system: shared company context, specialist agents, production workflows, and QA gates that can scale marketing output without separating speed from judgement.

## Status

Phase 2 foundation in progress: `marketing-system-setup` owns information-store
provisioning and a source-backed context build across company, product,
customer, competitive, commercial, measurement, brand, production, evidence,
and governance domains. The expanded local contract has not yet been published.
The shared `.agent-context/INDEX.md` read protocol is defined locally in
[`shared/context-read-protocol.md`](shared/context-read-protocol.md).

## Setup

Start with [SETUP.md](SETUP.md), then run the
[`marketing-system-setup`](marketing-system-setup/) skill.

## Who I am

Eoin Doyle — marketer and founder who builds with AI.
[LinkedIn](https://www.linkedin.com/in/eoindoyle/)

## License

[MIT](LICENSE) © Eoin Doyle
