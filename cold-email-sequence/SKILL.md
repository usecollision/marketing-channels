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

## Practitioner Grounding & Decision Rules

Built from Alex Berman (Experiment 27), Will Allred (Lavender), Steli Efti (Close), Morgan J. Ingram, Aaron Ross (*Predictable Revenue*), Dan Tyre, plus Mailshake State of Cold Email 2025 and Gmail's Feb 2024 sender rules. Full research: practitioner-intelligence/syntheses/outbound.md.

- **Offer > targeting > copy > infrastructure, in that causal order** (Berman — HEURISTIC, T1): fix the offer first ("the offer is the 80/20"), then targeting (JTBD-precise lists), then copy, then scale. The #1 practitioner convergence in outbound.
- **Reply rate is the north metric; opens are directional only** (Mailshake 2025 — EMPIRICAL, T1): 1-4% reply is the norm; only 16% of senders exceed 5%. Opens up + replies flat = offer problem, not copy.
- **Deliverability is infrastructure** (Berman + Gmail rules — FACT, T1): consistent daily caps (15-30/mailbox/day, never Monday bursts), ≤2 follow-ups within a week, warm domains. Gmail's 2024 rules (SPF/DKIM/DMARC, <0.3% spam, one-click unsubscribe for bulk) made this regulatory.
- **Fake personalization dies** (Berman/Efti/Allred — EMPIRICAL, T1): "Curious to know…" and template-inserted personalization are deleted instantly. Either genuinely personalize (real trigger + context) or lead offer-first with honest specificity.
- **Multichannel beats email alone** (Ingram/Tyre/Ross — HEURISTIC, T1): email + LinkedIn + phone + video cadences outperform pure email.

Decision rules:
1. IF a stranger wouldn't respond to the offer with zero risk THEN rebuild the offer before touching copy or lists (Berman — HEURISTIC, T1).
2. IF opens are healthy but replies are flat THEN the offer is broken — don't rewrite copy (Berman — HEURISTIC, T1).
3. IF reply rate <0.5-1% after 200-300 sends of a validated message THEN kill the message and change the offer or the list — not the subject line (synthesis — HEURISTIC, T2).
4. IF volume exceeds 15-30/mailbox/day or follow-ups exceed 2 within a week THEN throttle — volume spikes and over-follow-up train spam filters (Berman + Gmail docs — EMPIRICAL, T1).
5. IF personalization can't be genuinely researched (≥2-3 min/prospect) THEN go offer-first with honest specificity — a clean offer email beats a fake-personal one 9/10 (Berman — HEURISTIC, T1).
6. IF the prospect universe is LinkedIn-reachable THEN run multichannel (email + LI + phone/video) rather than email-only (Ingram — HEURISTIC, T1).
7. IF an explicit no arrives THEN stop that thread (yes/no are answers; "maybe" is death) (Efti — HEURISTIC, T1).
8. IF considering a 60-day re-contact cycle for a large TAM THEN it's a valid alternative to longer sequences — it trades depth for deliverability safety at volume (Berman — HEURISTIC, T2).

## Metrics

- **Reply rate** (north) — 1-4% norm; positive reply rate (meetings-positive replies per 1,000 sends) (Mailshake — EMPIRICAL, T1).
- **Meetings booked per 1,000 sends** — the pipeline conversion (synthesis — HEURISTIC, T2).
- **Deliverability**: inbox rate, spam complaints <0.3%, bounce rate — checked daily per domain (Gmail rules + Berman — FACT/EMPIRICAL, T1).
- **Per-touch response contribution** — which touch earns replies (Ross — HEURISTIC, T1).

## Practitioner-Sourced Failure Modes

- Bought/rented lists — never; list quality > copy (all practitioners — EMPIRICAL, T1).
- Volume spikes (1,000 Monday, none Tuesday) → near-certain spam (Berman — EMPIRICAL, T1).
- Fake personalization ("Curious to know…", pretend-knowledge inserts) (Berman/Efti/Allred — EMPIRICAL, T1).
- Pitching a service instead of an offer (Berman: zero-response campaigns until entry-point offer built — EMPIRICAL, T1).
- Irrelevant 11-touch stacks = interrupting 11x instead of once (Ingram — HEURISTIC, T1).
- Bolt-on copying of frameworks without the system — most Predictable Revenue copies failed (Ross — EMPIRICAL, T1).

## Sources

1. Alex Berman, offer-first + deliverability discipline essays (2026) | alexberman.com | tier 1 | 2026-08-15
2. Mailshake, State of Cold Email 2025 (n≈1,000 senders) | mailshake.com | tier 1 | 2026-08-15
3. Gmail/Yahoo bulk-sender guidelines (Feb 2024) | support.google.com | tier 1 (FACT) | 2026-08-15
4. Will Allred, personalization data (Lavender) | lavender.ai / LinkedIn | tier 3 (vendor self-reported) | 2026-08-15
5. Aaron Ross, Outbound Validation + retrospective | predictablerevenue.com / gtmnow.com | tier 1 | 2026-08-15
6. Morgan J. Ingram, multichannel cadence design | his SDR content | tier 2 | 2026-08-15
7. Steli Efti, sales email discipline | close.com blog | tier 1 | 2026-08-15

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