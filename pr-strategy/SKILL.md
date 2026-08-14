---
name: pr-strategy
category: pr
description: Design a PR strategy - narrative building, target publications, angle development, and share-of-voice measurement.
triggers:
  - "PR strategy"
  - "earned media plan"
  - "share of voice"
  - "media narrative"
  - "thought leadership plan"
  - "press coverage goals"
inputs:
  - brand_context
  - positioning_statement
  - product_news_inventory
  - competitor_coverage_report
  - spokespeople_list
outputs:
  - pr_strategy_doc
  - narrative_one_pager
  - angle_bank
  - target_publication_tiers
  - measurement_plan
related_skills:
  - press-pitching
  - press-release
  - newsjacking
  - podcast-appearances
  - product-launch-playbook
  - marketing-intelligence/positioning-framework
  - marketing-intelligence/competitor-audit
  - marketing-messaging/value-proposition
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- PR effort is ad hoc, with no narrative and no measurement
- Launching a product, funding round, or category initiative that deserves earned media
- Competitors dominate share of voice in your category
- Thought leadership is a stated growth goal for founders
- Stakeholder pressure requires proving PR ROI before scaling spend

## Workflow

### Step 1: Define the Narrative
A narrative is one story the market can repeat about you. Build it before targeting any publication:
- [ ] Run positioning inputs through the message house: category shift, differentiator, proof points
- [ ] Draft a one-paragraph narrative with three layers: (1) what the company believes, (2) what changed in the market, (3) proof we are right
- [ ] Pressure-test against a skeptic: would a journalist's audience care, or is this a press release wearing a costume?
- [ ] Pick 1-3 spokespeople and define what each owns (product vision, data, customers)
- [ ] Write the narrative one-pager — it feeds press-pitching and press-release downstream

**Gate:** One-paragraph narrative plus three proof points that survive the skeptic test.

### Step 2: Set Objectives and Capture the Baseline
Measure before you launch any campaign:
- [ ] Objectives: share of voice, referral traffic from media, backlinks from tier-1 outlets, brand search lift, inbound interview requests
- [ ] Baseline: capture current numbers for each (SOV via search-result counts for brand vs named competitors, analytics for referral traffic, backlink tool for links)
- [ ] Set targets as directional hypotheses, not promises — coverage volume is partly outside your control
- [ ] Agree the reporting cadence (monthly or quarterly) and the one dashboard where numbers live

**Gate:** Every objective has a captured baseline number and a target range.

### Step 3: Map Target Publications
- [ ] List tier-1 (national/business), tier-2 (trade/category), tier-3 (newsletters, podcasts, niche communities)
- [ ] For each, answer: which stories do they actually run, and why would they cover us now?
- [ ] Map publication -> beat -> named journalists (hand off to press-pitching for the contact list itself)
- [ ] Identify the 5-10 outlets that materially move your metric; weight effort there
- [ ] Note which formats each publication favors: data stories, op-eds, profiles, roundups

**Gate:** Tiered publication map with a why-us-why-now note per target.

### Step 4: Build the Angle Bank
A library of angles that survives slow news weeks:
- [ ] Angle types: original data, contrarian point of view, customer proof, category trend commentary, milestone or hire, instructional expert take
- [ ] Per angle record: headline idea, spokesperson, proof asset needed, target publications, expiration date
- [ ] Connect every angle to the Step 1 narrative — angles are doors into the same house
- [ ] Rank angles by news value x asset readiness; anything needing an asset gets one scheduled

**Gate:** 6-10 angles, each mapped to spokesperson, asset, and publication tier.

### Step 5: Build the Calendar and Integrate Channels
- [ ] Map angles to launch moments, seasonal hooks, and planned company news
- [ ] Sequence: exclusives to tier-1 first, then broader pitch, then owned and social amplification
- [ ] Plan a sustainable cadence — 1-2 substantive pitches per month is a reasonable starting pace for a small team (heuristic)
- [ ] Align with content-calendar, social, and email so earned coverage gets amplified
- [ ] Assign owners for monitoring, pitching, and measurement

**Gate:** 90-day calendar with owners, plus a channel amplification plan per angle.

### Step 6: Measure and Iterate
- [ ] Monthly: SOV movement, referral traffic by publication, backlinks won, brand search trend
- [ ] SOV method: compare count and visibility of brand mentions vs named competitors across your target publication set; keep the set constant so trends stay meaningful
- [ ] Referral traffic: tag campaign links, attribute by publication, watch for sustained lift vs a one-day spike
- [ ] Quarterly: kill angles that never landed, double down on publications that convert
- [ ] Feed lessons back into the angle bank and the narrative one-pager

**Gate:** One full measurement cycle completed and at least one strategy change documented from it.

## Practitioner Grounding & Decision Rules

Practitioners: Gini Dietrich (PESO model, Spin Sucks — T2), David Meerman Scott (newsjacking/real-time PR — T2), Ed Zitron (journalist-side PR reality — T2).

- IF owned content doesn't exist THEN build it before paid amplification — PESO handoffs: owned anchors, shared distributes, earned validates, paid amplifies what already works (Dietrich, FRAMEWORK, T2).
- IF goal includes AI-search/AEO visibility THEN prioritize earned + shared + organic owned content — >95% of links AI engines surface come from these (Dietrich as reported, EMPIRICAL, T2).
- IF a story breaks in your market and you have a legitimate tie THEN respond in hours, not days — "now means now"; journalists lift credible second-paragraph content while researching (Meerman Scott, FRAMEWORK, T1).
- IF your org can't approve/publish within ~4h THEN build that lane before relying on newsjacking (Meerman Scott, HEURISTIC, T2).
- IF a tactic's output can't be tagged to a business outcome THEN don't run it standalone — "your measurement problem usually isn't a measurement problem" (Dietrich, FRAMEWORK, T2).
- IF budget is tight THEN run owned+shared first; add paid only to amplify proven winners (Dietrich, FRAMEWORK, T2).
- IF planning a campaign THEN still leave reaction slots in the calendar — newsjacking lanes inside the system, not instead of it (synthesis Meerman Scott + Dietrich, HEURISTIC, T2).

## Metrics

- Primary: share of voice, coverage quality (tier of outlet, journalist reply rate), AI-citation mentions of brand, pipeline/reputation outcomes tagged per PESO channel.
- Guardrails: newsjacking pickup rate, owned-content share of total coverage, no AVE/vanity metrics.
- Timebox: quarterly PESO review; newsjacking reviewed per breaking story.
- When to re-measure: after any channel handoff change; if reply rate <5% over 20 pitches, rewrite pitch template before sending more.

## Sources

1. Dietrich, "The PESO Model — The MarComm Operating System" | https://spinsucks.com/peso-model/ | T1 | 2026-08-15
2. Meerman Scott, "Newsjacking!" | https://www.davidmeermanscott.com/blog/2011/11/newsjacking.html | T1 | 2026-08-15
3. Zitron, "5 reasons why reporters hate your PR pitches" | https://thenextweb.com/news/5-reasons-reporters-hate-your-pitches | T1 | 2026-08-15
4. Synthesis: syntheses/pr-launches.md | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Narrative | Generic claims | Story with proof points | Survives skeptic test, repeatable by others |
| Targets | Wishlist of big names | Tiered with beats | Tiered, beat-mapped, why-us-why-now per target |
| Angles | One announcement | A few angles | 6-10 angles with assets and owners |
| Measurement | No baseline | Baseline captured | Baseline + targets + attribution method |
| Integration | PR in a silo | Aligned with launch | Calendar synced with content, social, email |

### Common Failure Modes
- Pitching before a narrative exists — coverage lands, the message doesn't
- Chasing tier-1 vanity wins while ignoring trade outlets that drive actual signups
- No baseline, so every result is spun as success
- Angles that require assets nobody is scheduled to build
- Treating share of voice as exact science — methods are estimates; keep the measurement set stable and disclose the method in reporting
- Over-pitching the same narrative until journalists tune the company out
