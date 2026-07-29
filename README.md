# marketing-agent-system

Marketing agents and quality gates for AI-assisted production.

This repo starts with a setup agent and two public, company-configurable
LinkedIn skills:

- `marketing-system-setup` provisions the private company information store,
  creates `.agent-context/`, guides source collection, and builds durable
  marketing context before any production agents run.
- `linkedin-ghostwriter` writes founder or expert LinkedIn posts from a developed content idea, using a named author voice and a configured brand position.
- `linkedin-post-reviewer` reviews those posts before they ship, checking audience fit, lead frame, voice, product-pitch drift, hook strength, ending quality, banned words, and dialect.

The broader goal is a marketing-agent system: shared company context, specialist agents, production workflows, and QA gates that can scale marketing output without separating speed from judgement.

## Status

Phase 2 foundation in progress: `marketing-system-setup` now owns Stage 0
information-store provisioning.

## Setup

Start with [SETUP.md](SETUP.md), then run the
[`marketing-system-setup`](marketing-system-setup/) skill.

## Who I am

Eoin Doyle — marketer and founder who builds with AI.
[LinkedIn](https://www.linkedin.com/in/eoindoyle/)

## License

[MIT](LICENSE) © Eoin Doyle
