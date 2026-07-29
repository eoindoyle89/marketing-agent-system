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
| `customer-research` | Personal Vault | Packaged locally, not published | High overlap with Apache-2.0 installed `customer-research` | Context protocol wired; references copied; third-party notice added. |
| `competitor-profiling` | Personal Vault | Packaged locally, not published | No direct installed match found | Context protocol wired; references copied; creates competitor artifacts outside `.agent-context`. |
| `content-strategy` | Personal Vault | Packaged locally, not published | High overlap with Apache-2.0 installed `content-strategy` | Context protocol wired; references copied; third-party notice added. |
| `copywriting` | Personal Vault | Packaged locally, not published | High overlap with Apache-2.0 installed `copywriting` | Context protocol wired; references copied; third-party notice added. |
| `copy-editing` | Personal Vault | Packaged locally, not published | High overlap with Apache-2.0 installed `copy-editing` | Context protocol wired; references copied; third-party notice added. |
| `social` | Personal Vault | Packaged locally, not published | High overlap with Apache-2.0 installed `social-content` | Context protocol wired; references copied; social-listening references made agent-neutral; third-party notice added. |

### Wave 2: Search And Distribution

| Skill | Source folder | Status | Provenance flag | Packaging notes |
|---|---|---|---|---|
| `seo-audit` | Personal Vault | Not packaged | Similar to installed `seo-audit` | Requires careful references review. |
| `ai-seo` | Personal Vault | Not packaged | Similar to installed `ai-seo` | Time-sensitive tactics and platform claims need review before publication. |
| `site-architecture` | Personal Vault | Not packaged | Similar to installed `site-architecture` | Connect to public-asset audit and product capabilities. |
| `programmatic-seo` | Personal Vault | Not packaged | Similar to installed `programmatic-seo` | Needs data-source and proof constraints. |
| `schema` | Personal Vault | Not packaged | Similar to installed `schema-markup` | May remain technical and compact. |
| `aso` | Personal Vault | Not packaged | No direct installed match found | App-store specs may be time-sensitive. |
| `directory-submissions` | Personal Vault | Not packaged | No direct installed match found | Directory list needs provenance/currentness review. |
| `competitors` | Personal Vault | Not packaged | Similar to installed `competitor-alternatives` | Use only approved competitive claims. |

### Wave 3: Paid, Conversion, And Measurement

| Skill | Source folder | Status | Provenance flag | Packaging notes |
|---|---|---|---|---|
| `ads` | Personal Vault | Not packaged | Similar to installed `paid-ads` | Needs budget, goals, channel, and approval gates. |
| `ad-creative` | Personal Vault | Not packaged | Similar to installed `ad-creative` | Large reference set; package after context contract is proven. |
| `ab-testing` | Personal Vault | Not packaged | Similar to installed `ab-test-setup` | Needs metrics/funnel and experiment-history reads. |
| `analytics` | Personal Vault | Not packaged | Similar to installed `analytics-tracking` | Keep tool claims current and source system boundaries clear. |
| `cro` | Personal Vault | Not packaged | Similar to installed `page-cro` | Needs public-asset audit, funnel, campaign, and QA reads. |
| `signup` | Personal Vault | Not packaged | No direct installed match found | Connect to product funnel and activation context. |
| `onboarding` | Personal Vault | Not packaged | Similar to installed `onboarding-cro` | Connect to product capabilities and activation metrics. |
| `paywalls` | Personal Vault | Not packaged | Similar to installed `paywall-upgrade-cro` | Needs pricing and offer boundaries. |
| `popups` | Personal Vault | Not packaged | Similar to installed `popup-cro` | Needs channel and consent/compliance rules. |

### Wave 4: Lifecycle, Growth, And GTM

| Skill | Source folder | Status | Provenance flag | Packaging notes |
|---|---|---|---|---|
| `emails` | Personal Vault | Not packaged | Similar to installed `email-sequence` | Needs channel, consent, proof, and offer gating. |
| `cold-email` | Personal Vault | Not packaged | Similar to installed `cold-email` | Needs prospecting/compliance boundaries. |
| `sms` | Personal Vault | Not packaged | No direct installed match found | Consent/compliance rules need special care. |
| `churn-prevention` | Personal Vault | Not packaged | Similar to installed `churn-prevention` | Needs retention metrics and offer boundaries. |
| `referrals` | Personal Vault | Not packaged | Similar to installed `referral-program` | Needs offer/ops/legal gates. |
| `co-marketing` | Personal Vault | Not packaged | No direct installed match found | Needs partner permission and proof boundaries. |
| `community-marketing` | Personal Vault | Not packaged | Similar to installed `community-marketing` | Needs capacity and channel governance. |
| `launch` | Personal Vault | Not packaged | Similar to installed `launch-strategy` | Needs product readiness, proof, channels, and campaign history. |
| `lead-magnets` | Personal Vault | Not packaged | Similar to installed `lead-magnets` | Needs audience, proof, and data-capture policy. |
| `free-tools` | Personal Vault | Not packaged | Similar to installed `free-tool-strategy` | Needs engineering/resources and attribution rules. |
| `offers` | Personal Vault | Not packaged | No direct installed match found | Connect to offers/pricing ledger and proof limits. |
| `pricing` | Personal Vault | Not packaged | Similar to installed `pricing-strategy` | Needs pricing authority and effective dates. |

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

## Current Packaging Decision

Wave 1 is packaged locally. Do not push packaged skills until:

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
