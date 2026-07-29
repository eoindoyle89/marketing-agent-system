# marketing-system-setup

Provision the information store and setup context layer for the marketing agent
system.

This skill exists because marketing agents should not rely on chat memory. It
guides a user through creating or choosing a private GitHub-backed company
context repo, cloning it locally or choosing a local fallback, creating
`.agent-context/`, selecting an accepted source pool, auditing public assets,
and building source-backed context files.

## Use It When

- A company is starting with `marketing-agent-system`.
- A project needs durable company, product, customer, competitive, commercial,
  measurement, brand, proof, case-study, channel, operations, or QA context.
- Agents are producing generic or unsupported marketing output.
- A team needs a shared context store before scaling production.

## Stage 0

Stage 0 provisions the information store:

- explain private GitHub + local Markdown working copy;
- check whether Git/GitHub tooling is available;
- create or choose a private context repo;
- clone it locally or choose a local fallback;
- create `.agent-context/`;
- create `inbox/` and `attachments/`;
- verify the structure exists before Stage 1.

## Stage 1

Stage 1 builds the context:

- read public assets;
- show source-level public capture before presenting a confident public readout;
- read user-provided files from `.agent-context/inbox/`, an Obsidian vault, a
  local folder, a synced drive export, a system export, chat attachments, or
  individual files;
- create a source registry;
- present contradictions and a source map;
- interview the user across eight staged context domains;
- write context files;
- mark claim and approval status immediately when the user approves;
- create routing rules for downstream agents.

Detailed field contracts live in `references/context-schema.md`. The staged
questions and file ownership rules live in `references/interview-guide.md`.
The shared downstream read protocol lives in
`../shared/context-read-protocol.md` and is referenced from generated
`.agent-context/INDEX.md` files.
