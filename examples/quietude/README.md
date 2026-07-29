# Example: Quietude

Quietude is the fictional company used across this repo's examples (it also
anchors the `marketing-plan` skill's worked plan). Everything in this folder
is illustrative data with the real structure:

- [`.agent-context/`](.agent-context/) — a populated example of the company
  context store that `marketing-system-setup` builds: sources with IDs,
  a public-asset audit that stayed separate from approved truth, a
  proof-point ledger with statuses and boundaries, channel rules, QA policy,
  open questions, and a changelog that records approvals as they happen.
- [`worked-example.md`](worked-example.md) — one piece of work end to end:
  raw inputs → context store → article draft → review gate → recorded
  human approval.

Copy the structure, not the content. A real store is built by running
`marketing-system-setup` against your own sources.
