# Setup Fallback Manual

Use this when the AI cannot complete setup automatically.

The goal is simple: create a private company context folder, put source
material somewhere the AI can read it, and tell the setup agent where to look.

You do not need to understand Git, GitHub, command lines, or code to use this
fallback.

## When To Use This

Use this manual if the AI says it cannot:

- create folders;
- clone or create a GitHub repo;
- read a local file path;
- access your documents;
- browse your website or social accounts;
- run commands;
- copy files;
- continue after a permission error.

If the AI can do setup for you, use `start-here` and follow the agent.

## Option 1: Folder In Documents

This is the simplest fallback.

1. Open `Documents` on your laptop.
2. Create a folder called:

```text
Company Marketing Context
```

3. Inside that folder, create another folder called:

```text
.agent-context
```

4. Inside `.agent-context`, create two folders:

```text
inbox
attachments
```

5. Tell the AI:

```text
Use marketing-system-setup.

I am using a folder in Documents for my company context.
The folder is: [paste the folder path here]
```

If you do not know the folder path, tell the AI:

```text
I created the folder in Documents, but I do not know the path. Help me find it
one step at a time.
```

## Option 2: Existing Folder Or Vault

Use this if your company information already lives somewhere useful, such as an
Obsidian vault, a shared folder, a Drive export, or a folder of documents.

Tell the AI:

```text
Use marketing-system-setup.

I want to use this existing folder as the source pool:
[paste folder path]

Do not move or copy the source files unless I approve it.
```

The setup agent should index the source pool and write approved summaries into
`.agent-context/`.

## Option 3: Chat Attachments Only

Use this if the AI cannot read local folders, but you can attach documents in
chat.

Attach the files, then tell the AI:

```text
Use marketing-system-setup.

I am attaching source files in this chat. Treat them as the source pool for
setup. Create source IDs and tell me which information needs a durable local
copy later.
```

Good files to attach:

- website copy or page exports;
- pitch decks;
- product docs;
- customer interviews;
- testimonials;
- case studies;
- brand guidelines;
- campaign results;
- sales notes;
- pricing or offer docs.

Do not attach passwords, private keys, payment details, or unnecessary personal
data.

## If GitHub Does Not Work

GitHub is useful because it gives backup, version history, and collaboration.
It is not required for the first setup.

If GitHub login, repo creation, or cloning fails, tell the AI:

```text
Use the folder in Documents option for now. Record that GitHub backup is not
set up yet in open-questions.md.
```

Later, you can move the context folder into a private GitHub repo.

## If Browsing Does Not Work

The setup agent should review public information first, including the website
and social accounts. If the AI cannot browse, give it links or pasted text.

Tell the AI:

```text
Browsing is not available.

Here are the public assets to treat as source material:
- Website: [URL]
- LinkedIn: [URL]
- Other public assets: [URLs]

Ask me to paste page text if you cannot access them.
```

If needed, paste the important page text into chat and say:

```text
Treat this pasted text as public source material. Do not treat it as approved
company truth until I approve it.
```

## If The AI Cannot Read A Path

Try one of these:

1. Paste the full path again.
2. Move the files into `Documents/Company Marketing Context/.agent-context/inbox`.
3. Attach the files directly in chat.
4. Paste the relevant text into chat.

Then tell the AI:

```text
Use the source material I can provide here. Record any file-access limitation in
open-questions.md.
```

## If Setup Stops Halfway

You can resume setup.

Tell the AI:

```text
Use marketing-system-setup.

Resume setup from this context folder:
[paste folder path]

First, check what files already exist in .agent-context, then tell me the next
missing step.
```

The agent should not start over unless you ask it to.

## What The AI Should Create Eventually

The setup agent should create or complete this structure:

```text
.agent-context/
  INDEX.md
  sources.md
  public-asset-audit.md
  company-context.md
  product-capabilities-and-funnel.md
  positioning-and-icp.md
  customer-research-and-voc.md
  competitive-context.md
  offers-pricing-and-packaging.md
  goals-metrics-and-funnel.md
  marketing-operations.md
  brand-voice.md
  anti-ai-writing-rules.md
  visual-identity-and-assets.md
  proof-points.md
  case-studies.md
  channel-rules.md
  campaign-history.md
  qa-policy.md
  open-questions.md
  changelog.md
  inbox/
  attachments/
```

Do not worry if you cannot create all of these yourself. The setup agent should
create missing files when it has permission.

## What To Say When You Are Ready

Use this prompt:

```text
Use marketing-system-setup.

I am ready to set up the company context store.
I want to use: [private GitHub repo / existing folder / folder in Documents /
chat attachments].

Ask me one step at a time. Do not create folders, files, repos, commits, or
pushes without approval.
```

## After Setup

When setup is complete, use:

```text
Use marketing-orchestrator. I want to [describe the marketing outcome].
```

To bring the usage guide back:

```text
Use guide.
```
