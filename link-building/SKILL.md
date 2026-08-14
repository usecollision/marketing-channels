---
name: link-building
category: seo
description: Design and run a link-building program - prospecting, digital PR outreach, guest posting, and anchor text planning.
triggers:
  - "link building"
  - "backlinks"
  - "digital PR"
  - "guest posting"
  - "outreach campaign"
  - "domain authority"
  - "unlinked mentions"
  - "broken link building"
inputs:
  - website_url
  - competitor_urls
  - linkable_asset_inventory
  - brand_context
outputs:
  - prospect_list
  - outreach_sequences
  - pitch_templates
  - anchor_text_plan
  - link_tracking_sheet
related_skills:
  - seo-audit
  - technical-seo
  - serp-analysis
  - entity-optimization
  - content-calendar
  - marketing-intelligence/competitor-audit
  - marketing-messaging/case-study-builder
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Organic rankings are stuck despite strong on-page and technical work
- Competitors outrank you with clearly inferior content
- Launching a data study, tool, or guide that deserves coverage
- No structured link acquisition has happened in 6+ months
- New domain needs its first authority signals
- Digital PR moments exist (funding, data release, hiring a known expert)

## Workflow

### Step 1: Linkable Asset & Value Proposition Audit
Nobody links to a page that isn't worth linking to. Start here:
- [ ] Inventory existing assets: original data/studies, free tools, calculators, templates, definitive guides, strong opinions
- [ ] Score each asset: uniqueness, usefulness, freshness, emotional hook, source-ability (can a writer cite a number from it?)
- [ ] If nothing scores high, commission an asset first — data studies and free tools earn links far more efficiently than contact pages (heuristic from practitioner experience)
- [ ] Write one sentence per asset: who links to this, and why would they?

**Gate:** At least one asset cleared as "worth linking to", with a one-sentence linker persona and motivation.

### Step 2: Prospecting — Build the Target List
- [ ] Backlink gap: export competitor backlinks (Ahrefs/Semrush/Majestic), dedupe, filter for followable, relevant domains
- [ ] Resource pages: search "[topic] + resources/links/tools" — pages that exist to curate links
- [ ] Broken link targets: find dead outbound links on relevant pages; your asset as replacement
- [ ] Digital PR targets: journalists and newsletter writers who covered adjacent stories; build a media list
- [ ] Guest post targets: sites in adjacent (not identical) niches with active editorial calendars and real audiences
- [ ] Unlinked mentions: brands/tools that mention you without linking (set up alerts)
- [ ] Enrich every prospect: contact person, email, site metrics, last-active date

**Gate:** Prospect list of 50+ targets, deduplicated, enriched with contact info, tagged by acquisition method.

### Step 3: Prospect Qualification & Scoring
Rank prospects on relevance first, authority second:
- [ ] Relevance: does the site's audience overlap your ICP? (weight: high)
- [ ] Authority: domain rating/referring domains — use as a relative comparator against your niche, not an absolute truth (third-party metrics are estimates)
- [ ] Traffic and engagement: real audience, active comments/newsletter, recent publishing (weight: high)
- [ ] Red flags: link farms, PBN patterns (identical link profiles, spun content), paid-link marketplaces, sites that sell links openly — exclude
- [ ] Tier the list: Tier 1 (high relevance + authority, custom pitches), Tier 2 (scalable methods), Tier 3 (skip)

**Gate:** Every prospect has a score and tier; red-flag domains excluded with a reason logged.

### Step 4: Outreach & Pitching
- [ ] Digital PR: pitch a story, not a link — data angle, expert commentary, counter-narrative; target journalists with relevant beat history
- [ ] Guest posting: pitch 3 topic ideas per site, tailored to their gaps; deliver at or above their editorial quality bar
- [ ] Resource/broken-link pitches: one-paragraph value statement — what your asset is, who it helps, why it fits their page
- [ ] Personalization rules: reference a specific recent article or data point of theirs; no template spray
- [ ] Follow-up cadence: initial email + 2 follow-ups over ~2 weeks, each adding new value (heuristic), then drop silently
- [ ] Response handling: every reply answered within 24h; track objections (relevance, pay-for-placement) for pitch iteration

**Gate:** Outreach sequence launched to Tier 1 prospects with personalization verified per email; reply SLA defined.

### Step 5: Anchor Text Planning
- [ ] Distribution target (heuristic starting point, adjust by niche): branded/naked/URL anchors dominant (~60-70%), topical/partial-match (~20-30%), exact-match sparse (under ~10%)
- [ ] Map anchors to pages: exact-match only to money pages and sparingly; topical anchors to supporting assets
- [ ] Keep anchors varied and sentence-natural — identical anchor strings across many domains is a manipulation pattern
- [ ] Coordinate with internal linking: same anchor philosophy in your own site's links

**Gate:** Anchor text plan written per target page, with distribution ranges and natural-language anchor examples.

### Step 6: Tracking, Hygiene & Reporting
- [ ] Track: placements live, link indexation, anchor used, referral traffic, domain rating trend
- [ ] Monthly review: links gained vs lost, competitor delta, which method produced the most Tier-1 links
- [ ] Referral traffic check: a link nobody clicks still has value, but clicks reveal which audiences actually care
- [ ] Disavow as a last resort only — for clear spam attacks after removal requests fail
- [ ] Expectation setting: authority compounds over quarters, not weeks; report on trend, not weekly counts

**Gate:** Tracking sheet live with every placement logged; monthly report answers "which method earned the most valuable links this quarter?"

## Practitioner Grounding & Decision Rules

Built from Paddy Moogan (*The Moz Guide to Link Building*), Amanda Milligan (Fractl), Shannon McGuirk (Aira — digital PR), Joy Hawkins (local crossover). Full research: practitioner-intelligence/syntheses/seo.md.

- **Earned-only links; manipulation is pattern-detected** (Moogan — EMPIRICAL, T1): post-Penguin the numbers game died; 2026 SpamBrain 3.0 field data shows mass guest posts, PBNs, paid links, and exchanges being neutralized. If a tactic requires scale to work, it's a liability.
- **The sustainability test** (Moogan — FRAMEWORK, T1): "if links stop when outreach stops, it's not a strategy." Generalizable to any channel.
- **Expectation calibration** (McGuirk — EMPIRICAL, T1): digital PR campaigns yield 1-20 links normally; virality-chasing distorts expectations and budget.
- **Internal data first** (Milligan — EMPIRICAL, T1): original research on your own data earns links at scale; 40k+ link programs are built on data, not favors.
- **Digital PR consistency over virality** (McGuirk — HEURISTIC, T2): compounding beats spikes.

Decision rules:
1. IF a link tactic requires volume or automation to pay off THEN reject it — pattern detection neutralizes it eventually (Moogan + 2026 field data — EMPIRICAL, T1).
2. IF outreach stops and links stop THEN it wasn't a strategy — rebuild around assets that earn passively (original data, tools, expert commentary) (Moogan — FRAMEWORK, T1).
3. IF planning digital PR THEN expect 1-20 links per campaign and set budgets accordingly — virality is a bonus, not a plan (McGuirk — EMPIRICAL, T1).
4. IF the brand has internal data THEN make original research the anchor of the program before chasing placements (Milligan — EMPIRICAL, T1).
5. IF a target is a paid placement, exchange, or mass guest post THEN refuse — the link may be worth nothing or negative post-enforcement (Moogan/2026 data — EMPIRICAL, T1).
6. IF judging a program THEN track referring domains from earned sources and their downstream traffic, not raw link count (Moogan/McGuirk — FRAMEWORK, T1).

## Metrics

- **Earned referring domains** (not raw links) + their organic traffic contribution (Moogan — FRAMEWORK, T1).
- **Campaign yield distribution**: 1-20 links per digital PR campaign as the planning band (McGuirk — EMPIRICAL, T1).
- **Sustainability**: links earned without active outreach (Moogan — FRAMEWORK, T1).
- **Toxicity exposure**: share of portfolio from manipulative patterns — target 0 (2026 enforcement data — EMPIRICAL, T2).

## Practitioner-Sourced Failure Modes

- Pre-2012 tactics (directories, spun content, web 2.0) and modern equivalents (mass guest posts, PBNs, paid/exchanges) — dead or pattern-detected (Moogan; Optiseon 2026 — EMPIRICAL, T1).
- Virality-chasing PR that distorts expectations (McGuirk — EMPIRICAL, T1).
- Volume-first programs that stop when outreach stops (Moogan — FRAMEWORK, T1).
- Guest-post saturation in one niche — same sites, same audiences, diminishing value (2026 data — EMPIRICAL, T2).

## Sources

1. Paddy Moogan, *The Moz Guide to Link Building* | moz.com | tier 1 | 2026-08-14
2. Amanda Milligan, content-based link acquisition (Fractl studies) | fractl.com | tier 1 | 2026-08-14
3. Shannon McGuirk, digital PR link distribution data | Aira blog | tier 1 | 2026-08-14
4. Optiseon, 2026 link-building field report (SpamBrain 3.0 patterns) | tier 3 (vendor) | 2026-08-14

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Asset readiness | No linkable asset | Weak asset used | Asset scored and angle defined |
| Prospecting | Random outreach | Gap + resource lists | Multi-method list, scored and tiered |
| Personalization | Template spray | Some tailoring | Per-prospect relevance references |
| Anchor control | No plan | Basic ratios | Page-level plan with examples |
| Measurement | Nothing tracked | Placements tracked | Placements + indexation + traffic + trend |

### Common Failure Modes
- Buying links or link exchanges — penalties wipe out years of work
- Judging prospects by domain rating alone instead of relevance
- Exact-match anchor stuffing that trips spam patterns
- Pitching without a genuinely linkable asset
- No follow-up discipline — most placements happen on the second touch (heuristic)
- Chasing link volume while competitors win on one Tier-1 data story per quarter
