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
