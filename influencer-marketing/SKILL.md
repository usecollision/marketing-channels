---
name: influencer-marketing
category: creators
description: Run influencer campaigns - discovery and scoring, nano to macro tier strategy, briefs, campaign management, performance measurement, and disclosure compliance.
triggers:
  - "influencer marketing"
  - "influencer campaign"
  - "micro-influencer"
  - "creator campaign"
  - "influencer brief"
  - "sponsored content"
  - "influencer outreach"
  - "brand collab"
inputs:
  - campaign_goal
  - budget
  - icp
  - platform_priorities
  - content_rights_needs
  - measurement_setup
outputs:
  - tier_strategy
  - influencer_shortlist
  - scoring_model
  - creator_briefs
  - campaign_tracker
  - performance_report
related_skills:
  - creator-outreach
  - affiliate-program
  - partnership-strategy
  - social-strategy
  - youtube-strategy
  - marketing-intelligence/social-listening
  - marketing-messaging/video-scripts
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Planning an influencer or creator campaign and unsure which tier to bet on
- You need a discovery and scoring process instead of scrolling hashtags
- Briefs are being written per creator from scratch with inconsistent requirements
- Campaign performance needs measurement beyond follower counts and likes
- Sponsored content must meet disclosure and platform compliance requirements
- You want repeatable campaigns, not one-off creator deals

## Workflow

### Step 1: Set Goals and Choose the Tier Strategy
- [ ] Name the primary goal: awareness, engagement, conversions, or UGC volume for reuse — one primary
- [ ] Tier definitions as working ranges (heuristic — audit each creator's actual audience, don't rely on labels):
  - Nano (small followings, high trust) — best for authentic UGC volume and cost-effective testing
  - Micro (engaged niche audiences) — best balance of reach, relevance, and cost for most B2B and niche products
  - Macro (large reach) — best for category awareness and launch moments; pricier, lower engagement rates typical
  - Mega (celebrity tier) — launch splash only; treat as brand spend, not performance
- [ ] Split budget across tiers rather than betting it all on one big name (assumption — diversify risk, test, then concentrate on what works)
- [ ] Set per-goal metrics now: reach and CPM for awareness, engagement rate for engagement, tracked signups for conversion

**Gate:** Primary goal set, tier mix decided with budget split, per-goal metrics defined.

### Step 2: Discover and Score Creators
- [ ] Discovery sources: platform search and hashtags, competitor and adjacent brand collabs, creator marketplaces, social listening (see marketing-intelligence/social-listening), existing customers and fans
- [ ] Build the scorecard: audience-ICP fit, engagement rate vs follower count, content quality, brand-safety check, past brand-deal performance
- [ ] Vet authenticity: comment quality over comment count, follower growth patterns, engagement-to-follower ratio anomalies — bought audiences produce dead campaigns (assumption)
- [ ] Score 3-5x more creators than you need so negotiation has leverage and alternates exist
- [ ] Record evidence per score — the same discipline as any lead scoring, not vibes

**Gate:** Discovery run, 3-5x shortlist scored with evidence, authenticity checks passed.

### Step 3: Generate Briefs
- [ ] Brief components: goal, target audience, key messages, mandatory inclusions and exclusions, deliverables, timeline, disclosure requirement
- [ ] Give creators the problem to solve and the guardrails, not a script — over-scripted posts read as ads and underperform (assumption — validate with your own results)
- [ ] Include what makes your product credible for their audience specifically — not the homepage pitch
- [ ] Specify rights clearly in the brief: repurposing, paid amplification, duration — agree before content exists
- [ ] Keep the brief short — one page; creators skim, they don't study

**Gate:** One-page brief template with rights and disclosure clauses; tailored brief per creator.

### Step 4: Run Outreach and Negotiation
- [ ] Hand discovery output to creator-outreach for the outreach sequence and compensation playbook
- [ ] Budget sanity check per tier: list prices vary wildly by platform and niche — treat asking rates as opening positions, not truth (heuristic)
- [ ] Secure a small paid test with new creators before committing to bigger deals — derisks both sides
- [ ] Negotiate usage rights and exclusivity windows at the same time as price — never after content is live

**Gate:** Creators contracted with scope, price, rights, and exclusivity in writing.

### Step 5: Manage the Campaign
- [ ] One campaign tracker: creator, platform, deliverable, due date, status, live link, cost, results
- [ ] Approval process: check against brief and disclosure rules, then stop — over-editing strips authenticity
- [ ] Support live content: brand accounts comment and share, creators get engagement boosts that extend reach
- [ ] Track mid-flight: pause or re-allocate if early posts land far below benchmarks
- [ ] Keep creators informed of results — creators who see impact become repeat partners

**Gate:** Tracker live with all deliverables dated, approvals flowing, mid-flight checkpoints scheduled.

### Step 6: Measure and Stay Compliant
- [ ] Measure by goal: reach, CPM, engagement rate, tracked conversions via creator links or promo codes
- [ ] Disclosure compliance on every piece of sponsored content: platform tools and explicit labeling per FTC-style guidance in your region — no exceptions, no matter the tier (compliance is jurisdiction-specific — verify local rules)
- [ ] Archive every live post with its metrics — your benchmark library compounds
- [ ] Grade creators post-campaign: results vs scorecard predictions — the scorecard improves with every campaign
- [ ] Report blended cost per outcome (CPM, CPA) against other channels

**Gate:** Performance report by goal, disclosure audit passed, creators graded, benchmarks archived.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Tier strategy | One big name bet | Mixed tiers, no rationale | Goal-tied tier mix with diversified budget |
| Discovery | Scrolled hashtags | Multiple sources | 3-5x shortlist, scored with evidence, authenticity vetted |
| Briefs | Per-creator improvisation | Template exists | One-pager with rights, guardrails, and creative freedom |
| Management | Spreadsheet chaos | Tracker live | Approvals + mid-flight checks + creator feedback loop |
| Measurement | Follower counts | Engagement tracked | Goal-based blended CPM/CPA + disclosure audit + archived benchmarks |

### Common Failure Modes
- Judging creators by follower count instead of audience fit and engagement
- Buying fake-audience reach — dead campaigns with real invoices
- Over-scripted briefs that turn creators into banner ads
- Skipping disclosure — regulatory risk plus audience trust loss
- Measuring everything by last-click and calling the channel a failure
- No usage rights — you can't repurpose the one post that worked
- One-off deals with no data feedback loop — every campaign starts from zero
