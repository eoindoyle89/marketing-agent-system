# Skill Packaging Tracker

This tracker controls packaging the Personal Vault marketing skills into the
public `marketing-agent-system` repo.

Do not bulk-publish vault skills without a packaging pass. Each skill must be
made company-scalable, connected to `.agent-context/`, and checked for private
data and provenance risk.

## Packaging Rules

1. Preserve the shared context architecture.
2. Read `shared/context-read-protocol.md` before production, review, strategy,
   or analysis.
3. Replace vault-specific context loading (`AGENTS.md`,
   `.agents/product-marketing.md`, or Personal Vault assumptions) with
   `.agent-context/INDEX.md`.
4. Keep only reusable, company-neutral instructions.
5. Remove private company data, personal workflow assumptions, credentials,
   paths, and unsupported claims.
6. Keep resume, CV, job-application, and career-document work out of this repo.
7. Check provenance before publishing. Similarity to installed third-party
   skills must be treated as a review flag, and any derivative Apache-2.0
   content must retain license/notice files.
8. Keep skill bodies concise. Move detailed playbooks, templates, and examples
   to `references/` when useful.
9. Validate frontmatter and local links before commit.
10. Push only after explicit approval.

## Required Migration Block

Every packaged downstream marketing skill should include a context-loading
section equivalent to:

```markdown
## Context Loading

Before working, read `../shared/context-read-protocol.md` and follow it.

Use `.agent-context/INDEX.md` as the primary company context source when a
context store exists. Classify the request into the closest task family in the
index, read core files, then read required and conditional files for that task.

If the context store is missing, incomplete, stale, or contradicted, use the
shared protocol's `BLOCKED`, `PROCEED WITH LIMITATIONS`, or `PROCEED` decision
rule. Ask only for missing details that materially affect this task. Do not use
chat memory, public observations, or fallback configuration as approved company
truth.
```

Skills may add stricter reads, but should not bypass this block.

## Waves

### Wave 1: Foundation And Research

Package first because these feed many downstream skills and exercise the new
context model.

| Skill | Source folder | Status | Provenance flag | Packaging notes |
|---|---|---|---|---|
| `customer-research` | Personal Vault | Published in `beb4539` | High overlap with Apache-2.0 installed `customer-research` | Context protocol wired; references copied; third-party notice added. |
| `competitor-profiling` | Personal Vault | Published in `beb4539` | No direct installed match found | Context protocol wired; references copied; creates competitor artifacts outside `.agent-context`. |
| `content-strategy` | Personal Vault | Published in `beb4539` | High overlap with Apache-2.0 installed `content-strategy` | Context protocol wired; references copied; third-party notice added. |
| `copywriting` | Personal Vault | Published in `beb4539` | High overlap with Apache-2.0 installed `copywriting` | Context protocol wired; references copied; third-party notice added. |
| `copy-editing` | Personal Vault | Published in `beb4539` | High overlap with Apache-2.0 installed `copy-editing` | Context protocol wired; references copied; third-party notice added. |
| `social` | Personal Vault | Published in `beb4539` | High overlap with Apache-2.0 installed `social-content` | Context protocol wired; references copied; social-listening references made agent-neutral; third-party notice added. |

### Wave 2: Search And Distribution

| Skill | Source folder | Status | Provenance flag | Packaging notes |
|---|---|---|---|---|
| `seo-audit` | Personal Vault | Published in `a175f64` | High overlap with Apache-2.0 installed `seo-audit` | Context protocol wired; references copied; third-party notice added. |
| `ai-seo` | Personal Vault | Published in `a175f64` | High overlap with Apache-2.0 installed `ai-seo` | Context protocol wired; references copied; platform claims need currentness review before future revisions. |
| `site-architecture` | Personal Vault | Published in `a175f64` | High overlap with Apache-2.0 installed `site-architecture` | Context protocol wired; references copied; third-party notice added. |
| `programmatic-seo` | Personal Vault | Published in `a175f64` | High overlap with Apache-2.0 installed `programmatic-seo` | Context protocol wired; references copied; third-party notice added. |
| `schema` | Personal Vault | Published in `a175f64` | High overlap with Apache-2.0 installed `schema-markup` | Context protocol wired; references copied; third-party notice added. |
| `aso` | Personal Vault | Published in `a175f64` | No direct installed match found | Context protocol wired; references copied; app-store specs and benchmarks need currentness review before future revisions. |
| `directory-submissions` | Personal Vault | Published in `a175f64` | No direct installed match found | Context protocol wired; references copied; directory list and AI-search claims need currentness review before future revisions. |
| `competitors` | Personal Vault | Published in `a175f64` | High overlap with Apache-2.0 installed `competitor-alternatives` | Context protocol wired; references copied; third-party notice added. |

### Wave 3: Paid, Conversion, And Measurement

| Skill | Source folder | Status | Provenance flag | Packaging notes |
|---|---|---|---|---|
| `ads` | Personal Vault | Published in `524472b` | Similar to Apache-2.0 installed `paid-ads`; SKILL.md overlap ~52% | Context protocol wired; references copied; broken local tool registry links removed; budget, tracking, and approval gates added. |
| `ad-creative` | Personal Vault | Published in `524472b` | High overlap with Apache-2.0 installed `ad-creative`; SKILL.md overlap ~74% | Context protocol wired; references and asset copied; broken local tool registry links removed; creative approval boundary added. |
| `ab-testing` | Personal Vault | Published in `524472b` | High overlap with Apache-2.0 installed `ab-test-setup`; SKILL.md overlap ~96% | Context protocol wired; references copied; metrics, funnel, and QA reads added. |
| `analytics` | Personal Vault | Published in `524472b` | High overlap with Apache-2.0 installed `analytics-tracking`; SKILL.md overlap ~94% | Context protocol wired; references copied; broken local tool registry links removed; source-system boundaries added. |
| `cro` | Personal Vault | Published in `524472b` | High overlap with Apache-2.0 installed `page-cro`; SKILL.md overlap ~81% | Context protocol wired; references copied; form reference made agent-neutral. |
| `signup` | Personal Vault | Published in `524472b` | High overlap with Apache-2.0 installed `signup-flow-cro`; SKILL.md overlap ~95% | Context protocol wired; product funnel, activation, and QA reads added. |
| `onboarding` | Personal Vault | Published in `524472b` | High overlap with Apache-2.0 installed `onboarding-cro`; SKILL.md overlap ~91% | Context protocol wired; product capabilities, activation, and lifecycle reads added. |
| `paywalls` | Personal Vault | Published in `524472b` | High overlap with Apache-2.0 installed `paywall-upgrade-cro`; SKILL.md overlap ~91% | Context protocol wired; pricing, entitlement, and QA reads added. |
| `popups` | Personal Vault | Published in `524472b` | High overlap with Apache-2.0 installed `popup-cro`; SKILL.md overlap ~96% | Context protocol wired; channel, consent, frequency, and measurement reads added. |

### Wave 4: Lifecycle, Growth, And GTM

| Skill | Source folder | Status | Provenance flag | Packaging notes |
|---|---|---|---|---|
| `emails` | Personal Vault | Packaged locally, not published | Similar to installed `email-sequence` | Context protocol wired; references copied; tool-registry links removed; consent, offer, and send-approval gates added. |
| `cold-email` | Personal Vault | Packaged locally, not published | Similar to installed `cold-email` | Context protocol wired; references copied; compliance/lawful-basis gate and no-send boundary added. |
| `sms` | Personal Vault | Packaged locally, not published | No direct installed match found | Context protocol wired; references copied; tool-registry links removed; consent, quiet-hours, and no-send gates added; opt-in template links made placeholders. |
| `churn-prevention` | Personal Vault | Packaged locally, not published | Similar to installed `churn-prevention` | Context protocol wired; references copied; tool-registry links and CLI-tool table removed; billing/entitlement and save-offer authority gates added. |
| `referrals` | Personal Vault | Packaged locally, not published | Similar to installed `referral-program` | Context protocol wired; references copied; tool-registry links removed; incentive budget, legal/tax, and offers-ledger gates added. |
| `co-marketing` | Personal Vault | Packaged locally, not published | No direct installed match found | Context protocol wired; tool-registry links removed; partner permission, brand-use, and no-contact boundaries added. |
| `community-marketing` | Personal Vault | Packaged locally, not published | Similar to installed `community-marketing` | Context protocol wired; moderation-capacity and governance gates added; no live posting or moderation. |
| `launch` | Personal Vault | Packaged locally, not published | Similar to installed `launch-strategy` | Context protocol wired; tool link neutralized; readiness, embargo, and no-publish gates added. |
| `lead-magnets` | Personal Vault | Packaged locally, not published | Similar to installed `lead-magnets` | Context protocol wired; references copied; data-capture and consent-policy gate added. |
| `free-tools` | Personal Vault | Packaged locally, not published | Similar to installed `free-tool-strategy` | Context protocol wired; references copied; engineering-capacity and attribution gates added; example list scrubbed. |
| `offers` | Personal Vault | Packaged locally, not published | No direct installed match found | Context protocol wired; references copied; offers-ledger, proof-limit, and approval-authority gates added. |
| `pricing` | Personal Vault | Packaged locally, not published | Similar to installed `pricing-strategy` | Context protocol wired; references copied; pricing-authority and effective-date gates added. |

### Wave 5: Sales, Ops, Creative, And Strategy

| Skill | Source folder | Status | Provenance flag | Packaging notes |
|---|---|---|---|---|
| `prospecting` | Personal Vault | Not packaged | No direct installed match found | High compliance risk; package late. |
| `revops` | Personal Vault | Not packaged | Similar to installed `revops` | Needs system-of-record and lifecycle definitions. |
| `sales-enablement` | Personal Vault | Not packaged | Similar to installed `sales-enablement` | Needs approved claims, case studies, objections. |
| `public-relations` | Personal Vault | Not packaged | No direct installed match found | Media lists and pitch rules need provenance review. |
| `image` | Personal Vault | Not packaged | No direct installed match found | Needs visual assets and rights rules. |
| `video` | Personal Vault | Not packaged | No direct installed match found | Tool/vendor claims may be time-sensitive. |
| `marketing-ideas` | Personal Vault | Not packaged | Similar to installed `marketing-ideas` | Likely compact, but broad references need review. |
| `marketing-psychology` | Personal Vault | Not packaged | Similar to installed `marketing-psychology` | Needs claim/source caution for behavioural claims. |
| `marketing-council` | Personal Vault | Not packaged | No direct installed match found | Named advisor references need careful provenance/transform review. |
| `marketing-plan` | Personal Vault | Not packaged | No direct installed match found | Large strategy skill with many references; package after foundation wave. |
| `marketing-loops` | Personal Vault | Not packaged | No direct installed match found | Contains runtime/orchestration assumptions; package late. |
| `product-marketing` | Personal Vault | Not packaged | No direct installed match found | Likely superseded by `marketing-system-setup`; may become migration helper rather than public skill. |

## Wave 4 Provenance Review

The claude-cowork marketing plugin cache used for the Wave 1-3 line-level
comparisons was not available in the environment where Wave 4 was packaged.
The only installed analogue present (`email-sequence`, from a smaller
`marketing/1.2.0` plugin) shares only ~6% of non-empty lines with `emails`,
so it is not the analogue the pre-packaging flags refer to.

Wave 4 provenance flags are therefore carried over from the earlier local
comparison pass, not re-measured. The nine flagged skills (`emails`,
`cold-email`, `churn-prevention`, `referrals`, `community-marketing`,
`launch`, `lead-magnets`, `free-tools`, `pricing`) are listed in
`THIRD_PARTY_NOTICES.md` on that basis. Re-run the local line-level
comparison against the installed claude-cowork marketing plugin before
publishing Wave 4.

## Current Packaging Decision

Waves 1-3 are published (`beb4539`, `a175f64`, `524472b`). Wave 4 is
packaged locally, pending provenance re-measurement and approval. Do not push
future packaged skills until:

- each skill has the shared context-loading block;
- private/vault-specific references are removed;
- local references resolve;
- provenance flags are reviewed and notices are retained;
- the user approves publication.

## Wave 1 Provenance Review

Local comparison against the installed Anthropic Cowork marketing plugin found
high line-level overlap in five Wave 1 skills:

| Skill | Installed comparison | Approximate shared non-empty lines |
|---|---|---:|
| `customer-research` | `customer-research` | 79% |
| `content-strategy` | `content-strategy` | 87% |
| `copywriting` | `copywriting` | 82% |
| `copy-editing` | `copy-editing` | 78% |
| `social` | `social-content` | 68% |

The installed marketing plugin license observed locally is Apache-2.0. This repo
now includes `THIRD_PARTY_NOTICES.md` and
`LICENSES/Apache-2.0-Anthropic-Marketing.txt` so future publishing does not hide
that provenance.

## Wave 2 Provenance Review

Local comparison against the installed Anthropic Cowork marketing plugin found
high line-level overlap in six Wave 2 skills:

| Skill | Installed comparison | Approximate shared non-empty lines |
|---|---|---:|
| `seo-audit` | `seo-audit` | 73% |
| `ai-seo` | `ai-seo` | 73% |
| `site-architecture` | `site-architecture` | 84% |
| `programmatic-seo` | `programmatic-seo` | 83% |
| `schema` | `schema-markup` | 75% |
| `competitors` | `competitor-alternatives` | 79% |

`aso` and `directory-submissions` had no direct installed skill match in the
local comparison pass. Both still need currentness review because app-store
specs, benchmark claims, directory availability, and AI-search behaviour can
change.
