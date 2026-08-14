---
name: lead-sourcing-enrichment
category: outbound
description: Build clean outbound lead lists - multi-source sourcing, data provider selection, enrichment workflows, deduplication, quality scoring, and GDPR/CAN-SPAM compliance.
triggers:
  - "lead list"
  - "lead sourcing"
  - "lead enrichment"
  - "data enrichment"
  - "list building"
  - "data provider"
  - "deduplication"
inputs:
  - icp
  - existing_lists
  - lead_sources
  - budget
outputs:
  - source_plan
  - provider_shortlist
  - enrichment_workflow
  - dedupe_rules
  - quality_score
  - compliance_checklist
related_skills:
  - cold-email-sequence
  - multichannel-outbound
  - reply-classification
  - marketing-intelligence/account-intelligence
  - marketing-intelligence/icp-builder
  - marketing-intelligence/customer-research
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Starting outbound with no list
- Reply rates are low because of poor list quality
- Considering data providers or enrichment vendors
- Merging multiple legacy lists
- Compliance review before a new campaign

## Workflow

### Step 1: Source Design
Map every legal source before buying data:

- **First-party** - CRM history, signups, trial users, event attendees, webinar registrants, newsletter subscribers (highest quality, lowest risk)
- **Third-party providers** - contact databases, technographic, intent, and firmographic vendors
- **Public/derived** - company pages, directories, job postings as trigger signals (verify manual-collection rules per jurisdiction)
- **Intent signals** - hiring for relevant roles, funding events, tool adoption (see marketing-intelligence/intent-signals)
- **Partner/community** - co-marketing lists, community directories, marketplace profiles
- Score each source on quality, cost, coverage, freshness, and legal basis

**Gate:** Source inventory with per-source legality, cost, and quality notes.

### Step 2: Data Provider Selection
Evaluate providers against a consistent rubric:

- **Coverage** - match rate against your ICP titles/regions (ask for a sample test on your list)
- **Freshness** - update frequency and last-verified dates
- **Accuracy** - email/phone verification guarantees; ask about the verification method
- **Compliance** - GDPR processor status and data-origin transparency
- **Integration** - native CRM sync vs API/manual export
- **Pricing model** - per-contact, subscription, or credit-based; calculate cost per net-new valid lead (heuristic - cheap data with low validity costs more than priced data with high validity)

**Gate:** Shortlist of 2-3 providers with scored evaluation and test sample results.

### Step 3: Enrichment Workflow
- **Match keys** - email domain, LinkedIn URL, or company+name as the join key
- **Append fields** - title, seniority, company size, industry, location, tech stack, direct dial where compliant
- **Verification layer** - run every address through email verification (syntax, domain, MX, mailbox check); expect to drop invalid addresses (heuristic - meaningful drop rates on cold lists)
- **Freshness policy** - re-verify active segments on a quarterly cadence
- **Automation** - scheduled enrichment jobs in the CRM with field-level "enrichment source" and "last enriched" stamps

**Gate:** Documented enrichment pipeline with field map, verification layer, and refresh schedule.

### Step 4: Deduplication & Merge
- **Dedupe keys** - canonical email (lowercased) as primary key; company domain + normalized name as secondary
- **Fuzzy matching** - handle name variants and typos with conservative thresholds (avoid false merges)
- **Master record rules** - define which source wins per field (first-party beats third-party, newest beats oldest)
- **Merge audit trail** - keep a log of merged records for reversal
- **Lead-to-account** - link contacts to company records before scoring (see marketing-intelligence/account-intelligence)

**Gate:** Dedupe rules written, run on all lists, merge log verified.

### Step 5: List Quality Scoring
Score every lead for prioritization and send decisions:

- **Dimensions** - email validity, engagement history (if any), ICP fit, data freshness, source quality
- **Composite tiers** - A (verified + strong ICP fit) / B (verified, partial fit) / C (unverified or weak fit) / D (do not email)
- **Suppression** - hard-bounce, unsubscribe, complaint, and do-not-contact lists applied before every export
- **Quality gates** - only A/B tier enters cold outreach; C tier waits for enrichment or nurture
- **Ongoing measurement** - track bounce rate and reply rate per source; cut sources that underperform

**Gate:** Scored list with tier definitions and source-level performance tracking.

### Step 6: GDPR / CAN-SPAM Compliance
- **Legal basis** - documented legitimate-interest assessment for B2B processing; explicit consent for B2C
- **CAN-SPAM** - accurate sender, honest subject, physical address, and a working opt-out honored within 10 business days (statutory requirement)
- **GDPR** - privacy notice, data subject rights process, retention limits, and processor DPAs for any vendor touching EU data
- **Restricted categories** - healthcare, finance, and EU B2C require extra care; screen sources accordingly
- **Suppression everywhere** - every export, enrichment job, and sequence honors global suppression

**Gate:** Compliance checklist signed off before any list is loaded into outreach.

## Practitioner Grounding & Decision Rules

Built from Alex Berman, Aaron Ross, Mailshake State of Cold Email 2025, Gmail sender rules, plus 2026 provider-benchmark intel (Cleanlist/Apollo/ZoomInfo/Cognism tests, HubSpot data-decay numbers). Full research: practitioner-intelligence/syntheses/channels-longtail.md.

- **List quality > copy, in the causal order** (Berman/Ross — EMPIRICAL, T1): fix targeting before copy; a bad list defeats the best message. Bought/rented lists are banned (all practitioners + Gmail rules — T1).
- **Provider claims are hypotheses** (2026 benchmarks — EMPIRICAL, T3): field tests measured 78% (Apollo) vs 84% (ZoomInfo) email accuracy vs ~96% multi-source waterfall (vendor tests); claimed 91-98% figures are marketing. Test on your own list.
- **Data decays ~22.5% of B2B records per year** (HubSpot data via Cognism — EMPIRICAL, T2): re-verify active segments quarterly; trigger re-enrichment on bounce/form-resubmission signals.
- **Cost per usable record, not per lookup** (provider intel — HEURISTIC, T3): cheap data with low validity costs more than priced data with high validity.
- **Verification is a layer, not a feature** (synthesis — HEURISTIC, T2): ESPs flag bounce >5% (yellow) / >10% (red); at 1,000+ sends/week/rep, ~22% bounce trips spam filters within 2-4 weeks.

Decision rules:
1. IF considering a bought/rented list THEN never — permissionless sending destroys reputation and violates Gmail rules (all practitioners — EMPIRICAL, T1).
2. IF reply rate on a validated message is <1% after 200-300 sends THEN audit the list source before rewriting copy (Mailshake/Berman — EMPIRICAL, T1).
3. IF evaluating a provider THEN demand: upstream source count, SMTP verification method (syntax vs full handshake), refresh cadence, and a correction feedback loop; no answers = commodity resale (provider intel — HEURISTIC, T3).
4. IF a provider claims high accuracy THEN run a sample test on your own ICP list before committing (synthesis — HEURISTIC, T2).
5. IF active segments are older than a quarter THEN re-verify before the next campaign (data decay — EMPIRICAL, T2).
6. IF bounce rate on a source exceeds ~5% THEN cut volume and quarantine that source before it damages the domain (provider intel — EMPIRICAL, T3).
7. IF EU data is involved THEN require GDPR processor status + DPA + documented legitimate-interest basis (FACT — statutory).

## Metrics

- **Reply rate per 1,000 valid leads** — the quality metric that matters, tracked per source (synthesis — HEURISTIC, T1).
- **Bounce rate** — <2% target for outbound; >5% yellow / >10% red flags (provider intel — EMPIRICAL, T2/T3).
- **Source-level performance** — cut sources that underperform on validity or reply (Mailshake — EMPIRICAL, T1).
- **Match/fill rate on sample tests** — provider comparison on your own list (synthesis — HEURISTIC, T2).
- **Data freshness** — % of active records verified within 90 days (data decay — EMPIRICAL, T2).
- Re-measure: quarterly re-verification; monthly source scorecard.

## Practitioner-Sourced Failure Modes

- Buying the cheapest list and skipping verification — bounce spikes tank domain reputation (all — EMPIRICAL, T1).
- No dedupe — the same prospect hit by three sequences (synthesis — HEURISTIC, T2).
- Enriching with wrong-person data (name matches, wrong company) (synthesis — HEURISTIC, T2).
- Sending cold email to EU B2C contacts without consent (FACT — statutory).
- Ignoring suppression lists when switching tools (synthesis — HEURISTIC, T2).
- Scoring by volume instead of quality — reply rate per 1,000 valid leads is the metric (Mailshake — EMPIRICAL, T1).

## Sources

1. Alex Berman, offer-first + list discipline | alexberman.com | tier 1 | 2026-08-15
2. Mailshake, State of Cold Email 2025 | mailshake.com | tier 1 | 2026-08-15
3. Cleanlist, Apollo vs ZoomInfo 1,000-lead benchmark (78%/84%) + 15-provider landscape | cleanlist.ai | tier 3 (vendor, disclosed) | 2026-08-15
4. Cognism (citing HubSpot), data decay 22.5%/yr | cognism.com/blog/data-decay | tier 2 | 2026-08-15
5. Gmail/Yahoo bulk-sender requirements (Feb 2024) | support.google.com/mail/answer/81126 | tier 1 (FACT) | 2026-08-15
6. Synthesis: practitioner-intelligence/syntheses/outbound.md, channels-longtail.md | tier 1 | 2026-08-15

## Evaluation & QA

### List Quality Rubric
| Criteria | Weak | OK | Strong |
|----------|------|----|--------|
| Email validity | Unverified | Verification tool run | Verified + quarterly refresh |
| ICP fit | Title-only matching | Firmographic + title | + intent/trigger signals |
| Deduplication | None | Exact-match keys | Fuzzy + merge audit trail |
| Suppression | Manual | Global suppression list | Automated across all tools |
| Compliance | Unclear basis | Documented basis | Basis + DPAs + rights process |

### Common Failure Modes
- Buying the cheapest list and skipping verification (bounce spikes tank domain reputation)
- No dedupe - the same prospect hit by three sequences
- Enriching with wrong-person data (name matches, wrong company)
- Sending cold email to EU B2C contacts without consent
- Ignoring suppression lists when switching tools
- Scoring by volume instead of quality - reply rate per 1000 valid leads is the metric that matters
