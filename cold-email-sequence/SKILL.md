---
name: cold-email-sequence
category: outbound
description: Write high-converting B2B cold email sequences with research-driven personalization and follow-up strategy.
triggers:
  - "cold email"
  - "outbound email"
  - "email sequence"
  - "prospecting emails"
  - "outreach sequence"
  - "write cold emails"
inputs:
  - product_context
  - icp
  - prospect_research
  - value_proposition
outputs:
  - email_sequence
  - subject_line_variants
  - personalization_framework
  - follow_up_cadence
related_skills:
  - linkedin-outreach
  - deliverability-guide
  - marketing-intelligence/customer-research
  - marketing-messaging/conversion-copywriting
  - marketing-intelligence/competitor-audit
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:email
  - mcp:crm
version: 1.0.0
---

## When to Use

Invoke when:
- Building outbound as a growth channel
- Writing first cold email sequence for a new ICP
- Current sequences have <2% reply rate
- Launching outreach for a new product/market
- Refreshing stale sequences

## Workflow

### Step 1: Prospect Research Framework
Before writing any email, define your research protocol:

**Per-prospect research (30-60 seconds each):**
- Recent company news/announcements
- Their role and responsibilities
- Content they've published or shared
- Tech stack (for relevance)
- Mutual connections or shared experiences
- Specific trigger events (funding, hiring, product launch)

**Personalization tiers:**
| Tier | Research Depth | Use When | Expected Lift |
|------|--------------|----------|---------------|
| Hyper-personal | 5+ min research per prospect | Top 50 accounts | 3-5x reply rate |
| Segmented | 1 min, one personal detail | ICP-fit prospects | 2x reply rate |
| Templated | No research, strong offer | Scale testing | Baseline |

**Gate:** Research framework defined with clear triggers and personalization template.

### Step 2: Email 1 (Opening Email)
Structure: Short, relevant, one clear ask.

**Formula:** Relevance + Problem + Tease + CTA

`
Subject: [Short, curiosity-driven, no spam words] (3-5 words)

Hi [First Name],

[Personalization: 1 sentence showing you did research - their content, company news, role-specific challenge]

[Problem statement: 1-2 sentences about the pain they likely have - use customer language, not marketing speak]

[Tease: 1 sentence about how you solve this, with a specific proof point - customer result, metric, or unique approach]

[CTA: One simple, low-friction ask - not "book a demo" but "worth a quick look?" or "open to seeing how [company] did this?"]

[Sign-off]
`

**Rules:**
- Under 100 words (85 ideal)
- No attachments or links in first email
- Subject line: 3-5 words, lowercase, no clickbait
- One CTA only (not multiple asks)
- No "I" as the first word
- No "just checking in" or "I wanted to reach out"

Write 3 subject line variants + 2 body variants.

**Gate:** Email 1 is under 100 words, has personalization, and one clear low-friction CTA.

### Step 3: Follow-Up Sequence (Emails 2-5)
Build the sequence with different angles:

**Email 2 (Day 3): Add value**
- Share a relevant insight, resource, or observation
- Don't repeat email 1, add new information
- Soft CTA

**Email 3 (Day 7): Social proof**
- Customer story or result relevant to their situation
- Specific numbers/outcomes
- Direct CTA

**Email 4 (Day 14): Different angle**
- New pain point or use case
- Maybe reference a competitor or industry trend
- Direct CTA

**Email 5 (Day 21): Breakup**
- Acknowledge they're busy
- Offer to help in the future
- Light humor or memorable close
- "Should I close your file?" pattern

**Timing rules:**
- Email 1 → Email 2: 2-3 days
- Email 2 → Email 3: 3-4 days
- Email 3 → Email 4: 5-7 days
- Email 4 → Email 5: 7-10 days

**Gate:** 4-5 email sequence with different angles, appropriate timing, and escalating commitment.

### Step 4: Subject Line Optimization
Write 5+ subject lines per email using:

**Patterns that work:**
- Question: "quick question about [their challenge]?"
- Name drop: "[mutual connection] suggested I reach out"
- Relevance: "[their company] + [your value]"
- Curiosity: "[their competitor] is doing this differently"
- Direct: "[specific outcome] for [their role]"

**Patterns to avoid:**
- ALL CAPS or excessive punctuation!!!
- "Quick question" (overused)
- Clickbait that doesn't match body
- Generic ("Great opportunity", "Partnership")
- Spam trigger words (free, limited time, act now)

**Gate:** 3+ subject line variants per email, all under 5 words.

### Step 5: Quality Check & Deliverability
Before sending, verify:

**Copy quality:**
- [ ] Under 100 words per email
- [ ] Reads naturally (not robotic or templated)
- [ ] Personalization feels genuine (not fake)
- [ ] Each email could stand alone (not dependent on previous)
- [ ] CTA is specific and low-friction
- [ ] No spam trigger words

**Deliverability:**
- [ ] Sending domain warmed up (2+ weeks, gradually increased volume)
- [ ] SPF, DKIM, DMARC configured
- [ ] Custom tracking domain
- [ ] Daily send limit respected (<50/day per inbox for new domains)
- [ ] No purchased/scraped lists
- [ ] Unsubscribe mechanism included

**Gate:** All copy and deliverability checks pass.

## Evaluation & QA

### Cold Email Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Personalization | Generic template | Segment-level | Individual research visible |
| Brevity | 150+ words | 100-120 words | <85 words, every word earns its place |
| Relevance | Generic pitch | Industry-relevant | Role + company specific |
| CTA clarity | Vague or multiple asks | Clear ask | Low-friction, specific, easy yes |
| Sequence variety | Same angle repeated | Some variation | Each email adds new value/angle |

### Common Failure Modes
- Writing long emails (nobody reads 200+ word cold emails)
- Leading with "I" or your company (lead with THEM)
- Fake personalization ("I love your company" without specifics)
- Too many links/attachments (spam filters + feels salesy)
- Same angle in every follow-up (each email needs a new reason to reply)
- Not warming up sending domain (instant spam folder)