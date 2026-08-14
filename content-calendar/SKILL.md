---
name: content-calendar
category: content
description: Plan the editorial machine - topic to format to channel to cadence mapping with a working editorial workflow.
triggers:
  - "content calendar"
  - "editorial calendar"
  - "content planning"
  - "content cadence"
  - "what should we publish"
  - "topic backlog"
  - "editorial workflow"
  - "repurposing content"
inputs:
  - content_pillars
  - icp
  - topic_backlog
  - team_capacity
  - channel_mix
outputs:
  - calendar_template
  - format_channel_matrix
  - editorial_workflow
  - repurposing_cascade
  - cadence_plan
related_skills:
  - keyword-research
  - serp-analysis
  - social-strategy
  - youtube-strategy
  - linkedin-content
  - reddit-engagement
  - community-strategy
  - marketing-messaging/content-strategy
  - marketing-intelligence/icp-builder
  - marketing-intelligence/customer-research
  - marketing-intelligence/social-listening
required_context:
  - .context/product-marketing.md
allowed_tools: []
version: 1.0.0
---

## When to Use

Invoke when:
- Publishing is ad-hoc, driven by whoever shouts loudest
- Team wants a repeatable planning rhythm instead of weekly blank-page panic
- Topics exist but there's no mapping to formats, channels, or cadence
- Content gets published and then dies — no repurposing or distribution
- Need to align content output with SEO, social, and lifecycle priorities

## Workflow

### Step 1: Strategy Inputs & Content Pillars
- [ ] Gather inputs: ICP, funnel stages, campaign priorities, product roadmap, seasonal events
- [ ] Define 3-5 content pillars (the recurring themes every piece must serve); write one sentence per pillar
- [ ] Assign a pillar owner who can speak with real expertise — authority comes from people, not brands
- [ ] Set a time allocation across pillars (e.g. 40/30/20/10 — heuristic; adjust to strategy)

**Gate:** Pillars written, owned, and weighted; every future topic must map to a pillar or be rejected.

### Step 2: Topic Backlog & Scoring
- [ ] Merge topic sources: keyword-research gaps, serp-analysis briefs, customer questions (support, sales calls), objection mining, product launches, competitor content gaps
- [ ] Score each topic: audience fit, funnel stage, search demand, uniqueness, effort
- [ ] Keep a single ranked backlog — one source of truth, reviewed weekly
- [ ] Reject rules: topics that don't serve a pillar, can't be differentiated, or no one can speak on

**Gate:** Ranked backlog of 30+ topics with scores, sources, and rejection decisions logged.

### Step 3: Format → Channel → Cadence Mapping
- [ ] For each topic, pick the lead format: long-form article, video, thread, newsletter, tool, case study, event
- [ ] Map the lead format to its home channel, then plan the derivative formats per channel (see Step 5)
- [ ] Set cadence per channel honestly from capacity: e.g. one pillar article/week + one video + three social posts — frequency is a commitment, not a wish
- [ ] Balance the mix: evergreen vs timely, search vs social, top/middle/bottom funnel
- [ ] Reserve buffer capacity (~20% heuristic) for reactive moments and channel-native opportunities

**Gate:** Matrix published: pillar × format × channel × cadence, with per-week capacity that matches real team hours.

### Step 4: Editorial Workflow & Ownership
- [ ] Define pipeline stages: idea → brief → draft → review → scheduled → published → measured
- [ ] Assign roles per stage: writer, editor, SEO reviewer, approver; one DRI per piece
- [ ] Set SLAs per stage (e.g. draft in 5 days, review in 2 — heuristic, tune to team)
- [ ] Review gates: brand voice, claims/factual check, legal if applicable, SEO checklist
- [ ] Agree on tooling: calendar view, brief template, approval trail, scheduled publishing

**Gate:** Workflow documented with roles, SLAs, and gates; every active piece has a DRI and a due date.

### Step 5: Repurposing & Distribution Cascade
- [ ] Lead asset → derivatives: article → LinkedIn post, X thread, video script, newsletter section, Reddit-appropriate answer, community share
- [ ] Adapt, don't copy-paste: each channel gets a native rewrite (see channel skills for rules)
- [ ] Schedule the cascade explicitly in the calendar — distribution is a planned step, not an afterthought
- [ ] Cross-link assets (video embeds in article, article links in newsletter) to compound reach
- [ ] Assign internal amplification: team shares, customer advocacy asks where appropriate

**Gate:** Every lead asset has a scheduled cascade with at least 3 channel-native derivatives.

### Step 6: Calendar Ops & Review Rhythm
- [ ] Weekly planning session: pull next week's queue, confirm DRIs, catch slippage
- [ ] Monthly retro: what performed (reach, engagement, conversions), pipeline health, velocity vs capacity
- [ ] Reprioritize the backlog with performance data — kill rules: two failed iterations of a format gets retired
- [ ] Sync with campaign calendar: product launches, events, and seasonal moments reserved in advance
- [ ] Publish the calendar visibly so the whole company can plan around it

**Gate:** Weekly and monthly rhythms scheduled; performance data flows back into backlog scoring monthly.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Strategy link | Topics from whim | Some pillars | Pillars owned, weighted, enforced |
| Backlog | No backlog | List of ideas | Scored, ranked, sourced, rejected rules |
| Cadence | Unrealistic | Capacity-based | Capacity-based + buffer + honest mix |
| Workflow | No ownership | Roles defined | Stages + SLAs + gates + DRI per piece |
| Lifecycle | Publish and move on | Some repurposing | Scheduled cascade + retro loop |

### Common Failure Modes
- Building a calendar of dates before defining pillars — output without strategy
- Overcommitting cadence, then quietly dying out — publish less, consistently
- No DRI per piece — the calendar becomes a suggestion box
- Publishing lead assets with zero distribution cascade
- Never retiring formats or topics that keep underperforming
- Treating the calendar as fixed instead of a living prioritization artifact
