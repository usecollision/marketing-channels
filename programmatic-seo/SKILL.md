---
name: programmatic-seo
category: seo
description: Build programmatic SEO pages safely - templates, data sources, indexation architecture, and thin-content risk gates.
triggers:
  - "programmatic SEO"
  - "pSEO"
  - "generate pages at scale"
  - "template pages"
  - "long-tail pages"
  - "thin content risk"
  - "landing pages at scale"
  - "data-driven pages"
inputs:
  - product_context
  - keyword_research
  - data_source_inventory
  - competitors_in_vertical
outputs:
  - query_pattern_matrix
  - template_design
  - data_quality_plan
  - rollout_phases
  - thin_content_gates
related_skills:
  - keyword-research
  - technical-seo
  - serp-analysis
  - seo-audit
  - marketing-optimize/analytics-setup
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Your market has thousands of long-tail queries following repeating patterns
- You have (or can build) structured data that varies meaningfully per page
- Competitors dominate with template-generated pages and you have none
- Scaling content manually is too slow for the opportunity size
- An existing programmatic section is tanking after an algorithm update

## Workflow

### Step 1: Opportunity Model & Query Patterns
- [ ] Enumerate head terms (product category, use case, industry)
- [ ] Build the modifier matrix: "{head} for {use case}", "best {head} in {location}", "{tool A} vs {tool B}", "{metric} by {segment}"
- [ ] Validate demand per pattern: search volume, auto-complete suggestions, People Also Ask
- [ ] Check SERPs per pattern: does Google reward template pages here, or editorial depth? Intent varies by pattern — verify each one
- [ ] Size the opportunity: pattern count x modifier count = page universe; discard patterns with weak intent fit

**Gate:** Query pattern matrix written, each pattern validated against real SERPs and estimated demand, with a total page-universe size.

### Step 2: Data Source Selection & Quality
- [ ] Inventory candidate sources: internal databases, public datasets, third-party APIs, scraped-with-permission data
- [ ] Score each: freshness, granularity (enough unique fields per page), coverage (rows per pattern), license/rights, update mechanism
- [ ] Define the uniqueness contract: every page needs N genuinely different data points (heuristic: at least 3-5 distinct, user-relevant values per page — validate with your niche)
- [ ] Plan refresh cadence — stale data pages decay in rankings and trust
- [ ] Document data lineage: where each field comes from, how errors are caught

**Gate:** Data source(s) selected with uniqueness contract, refresh cadence, and lineage documented.

### Step 3: Template & Page Design
- [ ] Design page sections driven by data: computed summaries, comparison tables, charts, rankings — not just name swaps
- [ ] Add human-layer elements: methodology notes, editorial caveats, author/expert attribution, last-updated stamp
- [ ] Write variable copy rules: N sentence templates per section with placeholder rotation to reduce near-duplicate boilerplate
- [ ] Include UGC or third-party signals where available (ratings, usage data) to add trust depth
- [ ] Build one reference page by hand at editorial quality — this is the bar every generated page must meet

**Gate:** Reference page built and approved; template spec written with per-section data requirements and copy variation rules.

### Step 4: Architecture & Indexation
- [ ] URL structure: consistent, shallow, no session/parameter noise
- [ ] Hub-and-spoke internal linking: category hubs link to all pattern pages; related-page modules cross-link siblings
- [ ] Sitemap segmentation per pattern — lets you monitor and roll back pattern by pattern
- [ ] Crawl-budget guardrails: rollout in phases so bots discover quality pages first
- [ ] Canonical and noindex rules: non-unique permutations noindexed by default

**Gate:** Architecture spec approved: URL scheme, sitemap segmentation, internal-link rules, noindex policy.

### Step 5: Thin-Content Risk Gates
- [ ] Pre-launch quality checklist per pattern: uniqueness contract met, data verified, no placeholder text, schema valid
- [ ] Sample audit: manually review a random sample of ~50 generated pages against the reference page (heuristic sample size — scale with universe)
- [ ] Launch threshold: index only pages that pass the checklist; hold back or noindex the rest
- [ ] Phased rollout: start with a small slice (e.g. ~10% of the universe — heuristic), watch GSC behavior for weeks before scaling
- [ ] Kill switch: per-pattern noindex/sitemap removal path agreed before launch

**Gate:** Every page entering the index passed the checklist; phased rollout schedule and kill switch approved.

### Step 6: Measurement & Pruning
- [ ] Track per pattern: indexed count, impressions, clicks, CTR, conversion events
- [ ] Identify thin cohorts: crawled-but-not-indexed spikes, near-zero click pages, high bounce
- [ ] Prune or merge underperformers: consolidate near-duplicate pages, noindex dead-end patterns, redirect best-of sets into stronger pages
- [ ] Refresh data on schedule; re-audit templates quarterly against current SERPs
- [ ] Feed winning patterns back into keyword-research and content priorities

**Gate:** Monthly pSEO scorecard live: indexed %, traffic per pattern, thin-cohort list, and pruning actions taken.

## Practitioner Grounding & Decision Rules

Built from Kevin Indig (programmatic SEO + AI-search studies), Will Critchlow (SearchPilot testing), the 2024-26 scaled-content enforcement cases, plus the SEO synthesis (Gabe/Ray drop forensics). Full research: practitioner-intelligence/syntheses/channels-longtail.md.

- **Uniqueness floor per template** (Indig + enforcement cases — EMPIRICAL, T1): pages must differ in substance (3-5+ distinct user-relevant values), not one field. Mass near-identical pages are what 2024-26 scaled-content enforcement collapsed.
- **Ship in waves, monitor indexation** (Indig — HEURISTIC, T2): start ~10% of the universe, watch GSC indexation/volatility for weeks before scaling; per-pattern kill switch agreed before launch.
- **Test template changes at scale** (Critchlow — EMPIRICAL, T1): control-group tests on ≥100 similar pages; the −27% title-tag incident and boilerplate-removal negative are the canonical warnings against untested best-practice rollouts.
- **Templates decay** (Indig — EMPIRICAL, T1): publish-and-forget kills programmatic sections; refresh cadence + quarterly template re-audit are mandatory.
- **Diagnose before nuking** (Gabe/Ray — FRAMEWORK, T1): a tanking programmatic section gets cause-classified (relevancy/intent/quality) before remediation.

Decision rules:
1. IF a generated page duplicates another in substance THEN don't index it — enforce the uniqueness floor per template (Indig — HEURISTIC, T1).
2. IF launching a new pattern THEN ship a ~10% slice, monitor GSC indexation and volatility for weeks before scaling (Indig — HEURISTIC, T2).
3. IF changing a template element (title, boilerplate, structure) THEN test on a control set of ≥100 similar pages before full rollout (Critchlow — EMPIRICAL, T1).
4. IF a programmatic section tanks after an update THEN classify the cause (relevancy/intent/quality) before touching content or noindexing (Gabe/Ray — FRAMEWORK, T1).
5. IF a template cohort shows near-zero clicks/impressions for a quarter THEN merge, redirect, or noindex it — dead pages drag site quality (Indig — HEURISTIC, T2).
6. IF data freshness can't be maintained THEN don't launch the pattern — stale data pages decay in rankings and trust (Indig — EMPIRICAL, T1).

## Metrics

- **Per-pattern indexation rate** — indexed count vs submitted; crawled-but-not-indexed spikes flag thin cohorts (synthesis — HEURISTIC, T2).
- **Per-pattern traffic and CTR** — impressions, clicks, CTR, conversion events per pattern (synthesis — HEURISTIC, T2).
- **Template-change test results** — control-group deltas before rollout (Critchlow — EMPIRICAL, T1).
- **Uniqueness compliance** — sample audits (~50 pages per pattern) against the reference page (synthesis — HEURISTIC, T2).
- Guardrail: AI-citation share for programmatic content where the vertical is AI-sensitive (Indig — EMPIRICAL, T2).
- Re-measure: monthly pSEO scorecard; quarterly template re-audit against current SERPs.

## Practitioner-Sourced Failure Modes

- Publishing thousands of near-identical pages at once — the classic scaled-content enforcement trigger (Indig/SEL 2025 — EMPIRICAL, T1).
- One varying field (city-name swaps) called "programmatic SEO" (synthesis — HEURISTIC, T1).
- Untested template changes at scale — −27% title-tag incident (Critchlow — EMPIRICAL, T1).
- No pruning loop — dead pages accumulate and drag site quality signals (Indig — HEURISTIC, T1).
- Building the engine before one pattern is proven manually (synthesis — HEURISTIC, T2).
- Short-term testing of recovery — site-level quality re-rating is a multi-update game (Gabe — EMPIRICAL, T1).

## Sources

1. Kevin Indig, programmatic SEO rules + enforcement postmortems | growth-memo.com | tier 1 | 2026-08-15
2. Will Critchlow / SearchPilot, template-scale testing data | searchpilot.com | tier 1 | 2026-08-15
3. Search Engine Land, scaled-content enforcement cases (2025) via seo.md | tier 2 | 2026-08-14
4. Glenn Gabe / Jim Boykin-style drop forensics via syntheses/seo.md | tier 1 | 2026-08-14
5. Synthesis: practitioner-intelligence/syntheses/seo.md, channels-longtail.md | tier 1 | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Pattern validation | Assumed demand | Volumes checked | SERP intent verified per pattern |
| Data quality | One field varies | Several fields vary | Uniqueness contract + refresh plan |
| Page quality | Name-swap pages | Data-driven sections | Reference page + variation rules + E-E-A-T signals |
| Rollout control | Ship everything at once | Phased | Phases + gates + kill switch |
| Lifecycle | Publish and forget | Traffic tracked | Pruning, merging, quarterly re-audit |

### Common Failure Modes
- Publishing thousands of near-identical pages at once — a classic thin-content trigger
- Data with one varying field (city name swaps) treated as "programmatic SEO"
- Ignoring SERP intent: some patterns demand editorial depth, not templates
- No pruning loop — dead pages accumulate and drag down site quality signals
- Building the engine before proving one pattern works manually
- Treating programmatic pages as exempt from E-E-A-T standards
