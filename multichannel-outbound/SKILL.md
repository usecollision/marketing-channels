---
name: multichannel-outbound
category: outbound
description: Orchestrate outbound across email, LinkedIn, and phone - touchpoint design, cross-channel cadence, handoff rules, sequencing logic, and conversion tracking.
triggers:
  - "multichannel outbound"
  - "outbound cadence"
  - "multi-touch sequence"
  - "linkedin outbound"
  - "cold calling cadence"
  - "outbound orchestration"
inputs:
  - icp
  - offer
  - channel_capacity
  - crm_structure
outputs:
  - channel_map
  - cadence_blueprint
  - handoff_rules
  - sequence_flow
  - conversion_tracking_plan
related_skills:
  - cold-email-sequence
  - reply-classification
  - lead-sourcing-enrichment
  - domain-reputation-ops
  - marketing-optimize/crm-pipeline-attribution
  - marketing-optimize/utm-governance
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Designing a multi-touch outbound motion
- Email-only outreach has plateaued
- Adding LinkedIn or phone to an existing cadence
- Prospects respond on a different channel than the one you sent
- Reps juggle channels inconsistently

## Workflow

### Step 1: Channel Map & Capacity
- **Channels in scope** - email, LinkedIn (connect + DM), phone (call + voicemail), and optionally SMS (consent rules apply)
- **Per-rep capacity** - calls/day, LinkedIn actions/day, emails/day within deliverability caps (see domain-reputation-ops)
- **Per-channel rules** - LinkedIn connection limits (platform-enforced - keep well under daily caps to avoid restrictions), phone windows (business hours in prospect timezone), email volume caps
- **Audience x channel fit** - executives reply on LinkedIn, ops/IT on email, mid-market owners often answer phones; order the sequence around the ICP's dominant channel

**Gate:** Channel map with capacity numbers and audience-channel fit notes.

### Step 2: Cadence Blueprint
- **Total touches** - a common heuristic is 8-12 touches across channels over 3-4 weeks; adjust to sales cycle length and deal size
- **Spacing** - denser early (first 4 touches within 10 days), then widen; never more than one touch per channel per week per prospect
- **Touch mix per stage** - open with email or LinkedIn connect (context), reserve phone for warm follow-ups and high-fit accounts
- **Channel redundancy** - design each touch to stand alone; the prospect will only see a subset
- **Exit conditions** - hard stop on unsubscribe, explicit no (see reply-classification), or completed task

**Gate:** Blueprint written with per-day touch schedule, mix rules, and exit conditions.

### Step 3: Handoff & Sequencing Logic
- **Trigger-based switches** - channels change on events, not schedules: email → LinkedIn after 2 unanswered emails, LinkedIn → phone when the connection is accepted, phone → email voicemail follow-up
- **One narrative across channels** - each channel advances the same story angle; no contradictory messages
- **Personalization handoff** - research gathered for email gets reused in the LinkedIn note and the call intro
- **Rep handoffs** - SDR-to-AE handoff rules with CRM stage change and a context note (see reply-classification)
- **Time-of-day routing** - phone scheduled in prospect timezone; LinkedIn messages sent during working hours

**Gate:** Trigger-based handoff map covering every channel transition, written as if/then rules.

### Step 4: Message Design per Channel
- **Email** - under 100 words, one CTA (see cold-email-sequence)
- **LinkedIn connect note** - under 300 characters, no pitch, one reason to connect
- **LinkedIn DM** - 2-3 sentences after acceptance, value-first
- **Call opener** - permission-based, 15-second reason, then a question
- **Voicemail** - under 20 seconds, name + one reason + callback number
- **Shared voice** - same tone and vocabulary across channels (see marketing-messaging/brand-voice)

**Gate:** Per-channel templates with distinct lengths and one shared voice.

### Step 5: Conversion Tracking
- **Touchpoint logging** - every touch logged in CRM with channel, date, and outcome (connected, replied, booked, no-answer)
- **Source of reply** - capture which touch the prospect first responded to; this is the sequence's true conversion metric
- **UTM discipline** - consistent campaign/channel params across all outbound links (see marketing-optimize/utm-governance)
- **Stage mapping** - touchpoint outcomes map to pipeline stages (reply → qualified → meeting → opportunity)
- **Per-channel reporting** - reply rate, meeting rate, and cost per meeting by channel and sequence step; cut the worst step first

**Gate:** Tracking plan with CRM fields, UTM conventions, and a weekly sequence report.

## Practitioner Grounding & Decision Rules

Built from Morgan J. Ingram, Aaron Ross, Dan Tyre, Alex Berman. Full research: practitioner-intelligence/syntheses/outbound.md.

- **Multichannel beats single-channel** (Ingram/Tyre/Ross — HEURISTIC, T1): email + LinkedIn + phone + video cadences; email alone is the weakest channel. Touch variety matters: same-thread/new-thread, voicemail/no-voicemail, video/visual.
- **Fit > frequency** (Ingram — HEURISTIC, T1): an irrelevant 11-touch stack is interrupting 11x instead of once. Relevance per touch is the constraint on cadence length.
- **Cadence norms** (Ingram/Efti — HEURISTIC, T1): 6-11 touches over 3-4 weeks with variety; explicit no = stop.

Decision rules:
1. IF the prospect universe is reachable on 2+ channels THEN design a multichannel cadence (email + LI + phone/video) — never email-only (Ingram — HEURISTIC, T1).
2. IF a touch adds no new information or angle THEN cut it — relevance per touch is the constraint, not count (Ingram — HEURISTIC, T1).
3. IF an explicit no arrives THEN stop that thread; escalate to another channel only when there's a new trigger (Efti/Ross — HEURISTIC, T1).
4. IF sequencing THEN alternate channels and formats; a same-channel repetition stack is spam-shaped (Ingram — HEURISTIC, T1).
5. IF at enterprise scale THEN validate outbound experiments on small subsets before broad rollout (Ross — EMPIRICAL, T1).

## Metrics

- **Meetings booked per 1,000 touches**, by channel mix (Ross — EMPIRICAL, T1).
- **Per-touch response contribution** — kill touches that never earn replies (Ross — HEURISTIC, T1).
- **Reply rate** by channel (email vs LI vs phone) (Mailshake/Ingram — EMPIRICAL, T1).

## Sources

1. Morgan J. Ingram, multichannel cadence design | his SDR content | tier 2 | 2026-08-15
2. Aaron Ross, *Predictable Revenue* + Outbound Validation | predictablerevenue.com | tier 1 | 2026-08-15
3. Dan Tyre, outbound/sales practice (HubSpot) | tier 2 | 2026-08-15
4. Mailshake, State of Cold Email 2025 | mailshake.com | tier 1 | 2026-08-15

## Evaluation & QA

### Sequence Design Rubric
| Criteria | Weak | OK | Strong |
|----------|------|----|--------|
| Channel mix | Email only | 2 channels | 3 channels matched to ICP behavior |
| Handoff logic | Manual judgment | Fixed schedule | Trigger-based if/then rules |
| Cadence | Same message repeated | Varied angles | Each touch adds value |
| Tracking | Meetings only | Reply tracking | Touchpoint-level source-of-reply |
| Compliance | None | Unsubscribe honored | Consent + suppression across channels |

### Common Failure Modes
- Copy-pasting the email into LinkedIn DMs (platform norms differ, feels spammy)
- Too many touches too fast - burning prospects and domains simultaneously
- No trigger logic - reps guess when to switch channels
- Tracking only meetings - you cannot improve what you do not attribute to a touchpoint
- Phone calls without a scripted opener - rambling intros burn the list
- Sending connection requests and emails the same day with different angles (confusing)
