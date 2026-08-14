---
name: product-launch-playbook
category: launch
description: Coordinate a multi-channel launch - plan structure, asset checklist, channel sequencing, launch-day runbook, and post-launch measurement.
triggers:
  - "product launch"
  - "launch plan"
  - "launch checklist"
  - "launch day"
  - "go-to-market plan"
  - "release coordination"
inputs:
  - product_positioning
  - launch_date
  - channel_inventory
  - asset_inventory
  - launch_goal
outputs:
  - launch_plan
  - asset_checklist
  - channel_sequencing_map
  - launch_day_runbook
  - measurement_dashboard_spec
related_skills:
  - pr-strategy
  - press-release
  - product-hunt-launch
  - podcast-appearances
  - events-webinars
  - content-calendar
  - social-strategy
  - lifecycle-sequences
  - marketing-intelligence/gtm-plan
  - marketing-messaging/value-proposition
required_context:
  - .context/product-marketing.md
allowed_tools: []
version: 1.0.0
---

## When to Use

Invoke when:
- Coordinating a launch across 3+ channels (press, social, email, community, directories)
- A launch is 2+ weeks out and needs a plan instead of a checklist in someone's head
- Multiple owners are involved and handoffs keep dropping
- Past launches felt chaotic on the day and quiet after the week
- You need a reusable structure for recurring releases

## Workflow

### Step 1: Set Goals and Pick the Launch Tier
- [ ] Primary metric: signups, demos booked, revenue, or waitlist — exactly one north star for the launch window
- [ ] Secondary metrics: press coverage, community activity, referral traffic
- [ ] Tier decision: big-bang (all channels same day) vs rolling thunder (staged reveals) — big-bang for big news with an existing audience; rolling for niche or complex products (heuristic)
- [ ] Define what "success" is for day 1, week 1, and day 30

**Gate:** One north-star metric, a tier decision, and success thresholds written down.

### Step 2: Build the Asset Checklist
| Channel | Assets |
|---|---|
| Press | press release, pitch list, embargo agreement |
| Email | launch announcement, segment variants, lifecycle trigger updates |
| Social | post copy per platform, images or video, thread scripts |
| Community | announcement template, FAQ, mod and ambassador brief |
| Directories | Product Hunt page, HN post, BetaList submission |
| Website | launch page, changelog, docs, pricing updates |
| Internal | support brief, sales enablement, on-call plan |
- [ ] Assign every asset an owner and a done-by date
- [ ] Apply the no-asset-orphan rule: every channel activity has its assets listed in this table

**Gate:** Full asset checklist with owners and dates; no channel planned without assets.

### Step 3: Sequence Channels and Build the Timeline
- [ ] T-30: lock positioning and messaging, start asset production
- [ ] T-14: press exclusive offers out, community previews, beta users briefed
- [ ] T-7: all assets final, email and social scheduled, war-room dry run
- [ ] T-3: embargo confirmations, support and sales briefed
- [ ] T-0: launch-day runbook executes (Step 5)
- [ ] T+7: momentum push (week-2 content, customer stories)
- [ ] Sequencing rule: exclusive press or community gets it first; broad channels follow within hours; owned channels always on time, never early

**Gate:** Timeline exists with every asset mapped to a date and an owner.

### Step 4: Pre-Brief Partners and Supporters
- [ ] Customers for quotes and testimonials — ask before the launch, confirm quote text in writing
- [ ] Community leaders, moderators, and ambassadors — brief with FAQ and talking points
- [ ] Press contacts — exclusives and embargoes handled per press-pitching rules
- [ ] Internal teams — support knows what changed, sales knows the pitch, engineering knows the on-call plan
- [ ] Partners and affiliates — provide assets and links in advance

**Gate:** Every partner and internal team briefed and confirmed before T-3.

### Step 5: Run Launch Day
- [ ] Runbook format: time | action | owner | channel | link — pre-filled the day before
- [ ] Sequence: product live and verified -> press and community posts -> email send -> social bursts -> monitoring
- [ ] War room: one shared channel, a named incident owner, an escalation path for outages
- [ ] Every inbound mention answered same-day (comments, replies, PH, HN, social)
- [ ] Log everything: sends, posts, coverage, signup spikes — the dashboard spec from Step 1 gets populated

**Gate:** Runbook executed end to end with zero missed scheduled items; all inbound responded to within the day.

### Step 6: Measure and Build Momentum
- [ ] Checkpoints at 24h, 72h, 7d, and 30d against the Step 1 thresholds
- [ ] Day-7 momentum: publish customer stories, post the launch data recap, run a follow-up webinar or AMA
- [ ] Week-2 retrospective: what landed, what flopped, what was missing
- [ ] Update the asset checklist and runbook with every lesson — the playbook compounds

**Gate:** All checkpoints measured and a retrospective written with concrete playbook changes.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Goals | "Get attention" | One metric | Metric + thresholds + secondary signals |
| Assets | Missing assets found on launch day | Checklist complete | Checklist + owners + dates |
| Sequencing | Everything same day, no plan | Timeline exists | Staged reveals with embargo alignment |
| Day-of | Ad hoc | Runbook exists | Runbook executed, inbound handled same-day |
| Post-launch | Nothing after day 1 | Checkpoints measured | Momentum push + retrospective shipped |

### Common Failure Modes
- Launch day is the plan — no T-30 to T-7 build-up means the day lands flat
- Assets discovered missing on launch day because nobody owned the checklist
- Posting on owned channels before the agreed embargo lifts
- No single metric, so the launch is "successful" by committee
- Stopping at day 1 — most launches are made or lost in weeks 1 and 2
