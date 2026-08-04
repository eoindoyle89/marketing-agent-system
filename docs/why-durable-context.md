# Why Durable Context Matters

A case study in why this repo is an architecture, not a prompt library.

## The failure mode

Ask a capable AI model for "a LinkedIn article about our product" and you
get fluent text with three defects that don't show up until they cost you:

1. **Invented facts.** The model fills gaps with plausibility — numbers that
   were never measured, customers that don't exist, claims legal never saw.
2. **Generic voice.** Without durable voice rules it reverts to the mean of
   the internet: the same words, the same rhythm, the same endings as
   everyone else's AI content.
3. **Amnesia.** Whatever you taught it in chat evaporates. The next session,
   or the next tool, starts from zero — so quality depends on who happened
   to paste what into which conversation.

Teams patch this with longer prompts. Prompts don't fix it, because the
problem isn't instruction — it's that the facts live nowhere.

## The architecture answer

This system moves company truth out of chat and into a store the agents
must read: `.agent-context/`, a folder of Markdown files in a private repo,
built once by a setup agent and maintained under explicit governance.

Three design decisions do the real work:

**Public assets are observations, not truth.** The setup agent audits the
website first and records what the market sees — then treats every claim on
it as unconfirmed until a human promotes it. In the
[Quietude example](../examples/quietude/.agent-context/public-asset-audit.md),
the website and the investor deck disagreed about a headline number; the
system surfaced the contradiction and a human chose the approved wording.
A prompt-based workflow would have shipped whichever number the model saw
last.

**Claims are a ledger, not a vibe.** Every public-facing claim lives in
[`proof-points.md`](../examples/quietude/.agent-context/proof-points.md)
with a status (`Approved`, `Use With Boundary`, `Unverified`,
`Contradicted`, `Retired`), a source, allowed wording, and a recorded
boundary — "peer-reviewed research found measurable effects" is usable;
"clinically proven" is forbidden by name. Drafting agents can only write
what the ledger permits. The interesting result isn't what the example
article says; it's what it *couldn't* say.

**Skills are stateless; the store is the interface.** None of the specialist
skills contain company facts. Each declares what context it
reads and follows one shared protocol: index first, task family, required
files, claim boundaries, report limitations. Change your positioning once
in the store and every skill — copywriting, ads, SEO, lifecycle, the
review gates — picks it up on its next run. That is what makes the system
company-scalable rather than a pile of tuned prompts for one business.

## The QA layer

Generation and judgment are separated. Review-gate skills load the same
context independently and run named, failable tests — audience, lead
frame, thesis, proof discipline, banned language — returning quoted
violations with fixes, not adjectives. And the last step is structurally
human: agents cannot publish, send, spend, or approve claims. Approvals
are scoped and written to a changelog the moment they happen.

## What to look at

- The [worked example](../examples/quietude/worked-example.md): raw inputs
  → store → draft → review gate → recorded approval, end to end.
- The [example store](../examples/quietude/.agent-context/) itself — the
  artifact everything else reads.
- [`shared/context-read-protocol.md`](../shared/context-read-protocol.md)
  — the contract that makes the skill library behave like one system.

Durable context is slower to set up than a clever prompt. It is also the
difference between AI marketing output you have to police and AI marketing
output you can approve.
