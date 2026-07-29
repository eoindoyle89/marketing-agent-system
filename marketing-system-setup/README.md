# marketing-system-setup

Provision the information store and setup context layer for the marketing agent
system.

This skill exists because marketing agents should not rely on chat memory. It
guides a user through creating or choosing a private GitHub-backed company
context repo, cloning it locally or choosing a local fallback, creating
`.agent-context/`, collecting source files, auditing public assets, and building
source-backed context files.

## Use It When

- A company is starting with `marketing-agent-system`.
- A project needs durable brand, proof, case-study, and channel context.
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
- read user-provided files;
- create a source registry;
- interview the user in stages;
- write context files;
- mark claim status;
- create routing rules for downstream agents.
