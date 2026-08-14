---
name: serp-analysis
category: seo
description: Analyze SERP feature landscapes - intent classification, featured snippets, People Also Ask, and ranking opportunity scoring.
triggers:
  - "SERP analysis"
  - "search intent"
  - "featured snippets"
  - "People Also Ask"
  - "SERP features"
  - "ranking opportunity"
  - "why is this ranking"
  - "share of SERP"
inputs:
  - keyword_list
  - target_urls
  - competitor_urls
  - serp_data_exports
outputs:
  - intent_map
  - serp_feature_landscape
  - opportunity_scorecard
  - content_briefs
  - cannibalization_report
related_skills:
  - keyword-research
  - seo-audit
  - ai-search-audit
  - entity-optimization
  - programmatic-seo
  - content-calendar
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Rankings are decent but traffic is flat — the SERP layout may be stealing clicks
- Deciding which keywords are actually winnable before writing content
- Competitors own featured snippets or AI Overview citations that should be yours
- Content keeps cannibalizing itself across similar keywords
- Prioritizing between keyword opportunities for the quarter

## Workflow

### Step 1: Build the Keyword-SERP Dataset
- [ ] Assemble the keyword set (from keyword-research) plus any terms where you already rank on page 1-2
- [ ] Pull live SERPs per keyword, capturing: full result set, positions, and every feature present
- [ ] Record features per keyword: featured snippet, People Also Ask, AI Overview, video carousel, image pack, local pack, shopping, knowledge panel, discussions
- [ ] Snapshot competitor presence: which domains appear in which features

**Gate:** Dataset covering every target keyword with feature-level SERP detail, stored for longitudinal comparison.

### Step 2: Intent Classification
- [ ] Classify each keyword: informational, commercial investigation, transactional, navigational, local
- [ ] Read the top 3 results to confirm intent — a keyword's words can lie; the SERP tells the truth
- [ ] Map each keyword to funnel stage and to a target page type (article, comparison, product, location page)
- [ ] Flag intent mismatches: keywords you rank for where your page type doesn't match what the SERP rewards

**Gate:** Every keyword carries an intent label, funnel stage, and expected page type — verified against live results.

### Step 3: SERP Feature Landscape Mapping
- [ ] Build the feature frequency table: which features appear on what share of your keywords
- [ ] Identify feature ownership: who currently wins each snippet, PAA cluster, and AI Overview citation
- [ ] For AI Overviews: log which sources are cited — this doubles as ai-search-audit input
- [ ] Compute share-of-SERP: even without ranking #1, features (PAA, snippets, images) can capture visibility
- [ ] Note "zero-click" keywords where features dominate and a top-3 rank may convert poorly

**Gate:** Feature landscape table per keyword cluster, with current winners and citation sources documented.

### Step 4: Ranking Opportunity Scoring
- [ ] Score each keyword: current position, feature winnability (structural gap analysis — is a snippet answerable in 40-60 words? does a PAA cluster exist?), difficulty, business value
- [ ] Combine into tiers: Tier 1 (ranked 4-15 + winnable feature), Tier 2 (ranking 2-3 but losing features), Tier 3 (out of reach or low value)
- [ ] Flag cannibalization: multiple of your URLs competing for the same intent
- [ ] Produce the opportunity scorecard: keyword, intent, feature target, current owner, effort, expected value

**Gate:** Scorecard ranked by expected value with clear tiers — a defensible prioritization artifact, not a hunch list.

### Step 5: Content & Structure Recommendations
- [ ] For snippet targets: exact answer format (definitional sentence, table, list) matching the current winner's structure
- [ ] For PAA targets: question-answer sections mapped to the real PAA questions on the SERP
- [ ] For AI Overview citation targets: cite-worthy content — direct answers, sourced statistics, comparison tables
- [ ] For cannibalization: consolidate, redirect, or re-differentiate competing pages with distinct intents
- [ ] Hand recommendations to content-calendar as briefs with the SERP evidence attached

**Gate:** Each Tier 1 keyword has a structural brief; cannibalization pairs have a resolution decision.

### Step 6: Monitor & Iterate
- [ ] Re-pull the dataset on a cadence (monthly for core terms, quarterly for the tail — heuristic)
- [ ] Track feature wins/losses: snippets gained, PAA presence, AI Overview citations
- [ ] Record ranking and visibility changes next to each previous snapshot
- [ ] Feed learnings back: winning formats into content briefs, losing patterns into the next iteration

**Gate:** Before/after comparison run on schedule; wins and losses attributed to specific changes, not coincidence.

## Practitioner Grounding & Decision Rules

Built from the SEO synthesis (Ahrefs intent framework, Soulo, Dunning, Tom Capper) plus the AEO synthesis (Indig's AI-citation decoupling, Solis topic aggregation, Law/Guan CTR data). Full research: practitioner-intelligence/syntheses/channels-longtail.md.

- **Intent is read from the SERP, not the keyword** (Ahrefs/Soulo/Dunning — EMPIRICAL, T1): volume is a trap; traffic potential and bottom-funnel intent are the real filters. The SERP decides format.
- **Correlations are hypotheses** (Capper — FRAMEWORK, T1): any ranking-factor claim gets the four-explanation filter (causation / reverse causation / confounding / coincidence) before spend.
- **AI citations decouple from rankings** (Indig — EMPIRICAL, T1): classic SERP #1 can have zero AI citations; track presence/portability/concentration per engine, never a blended score.
- **Treat each AI answer as a sample** (Solis — HEURISTIC, T1): aggregate at topic level over 50-200 prompts; never act on 1-2 answers.
- **AIO compresses clicks** (Law/Guan — EMPIRICAL, T1): AIO presence correlates with −34.5% position-1 CTR — features and citations are visibility, not just rank.

Decision rules:
1. IF volume is high but the live SERP shows a different intent than your page type THEN deprioritize — the SERP tells the truth (Soulo/Dunning — EMPIRICAL, T1).
2. IF a correlation claims a ranking factor THEN run Capper's four-explanation filter before allocating budget (Capper — FRAMEWORK, T1).
3. IF an AI Overview is present on a target query THEN expect compressed CTR and target features/citations rather than position 1 alone (Law/Guan — EMPIRICAL, T1).
4. IF tracking AI visibility THEN measure presence/portability/concentration per engine at topic level (50-200 prompts) — a blended score hides single-engine concentration (Indig — EMPIRICAL, T1).
5. IF 1-2 SERPs suggest a pattern THEN verify at topic level before acting (Solis — HEURISTIC, T1).
6. IF chasing a featured snippet THEN match the current winner's structure (definitional sentence, table, list) and check the intent matches your page type (synthesis — HEURISTIC, T2).

## Metrics

- **Intent map coverage** — every target keyword labeled + verified against live top-3 results (synthesis — HEURISTIC, T2).
- **Feature landscape stats** — feature frequency share, current owners, snippet/PAA/AIO citation wins per keyword (synthesis — HEURISTIC, T2).
- **AI citation metrics** — presence %, portability %, concentration % per engine, tracked quarterly (Indig — EMPIRICAL, T1).
- **CTR vs AIO-free peers** — position-1 CTR delta on queries with vs without AIO (Law/Guan — EMPIRICAL, T1).
- **Opportunity scorecard accuracy** — wins/losses attributed to specific changes each cycle (synthesis — HEURISTIC, T2).
- Re-measure: monthly for core terms, quarterly for the tail; before/after comparison on schedule.

## Practitioner-Sourced Failure Modes

- Judging opportunity by search volume instead of the actual SERP layout (Soulo — EMPIRICAL, T1).
- Assuming a #1 rank means full visibility — features and AIO can compress or steal the click (Law/Guan — EMPIRICAL, T1).
- Acting on single-answer AI samples instead of topic-level aggregation (Solis — HEURISTIC, T1).
- Treating AI Overview citations as separate from classic SERP analysis — one dataset, two readouts (Indig — EMPIRICAL, T1).
- Pulling SERPs once and never re-measuring — landscapes shift quarterly (synthesis — HEURISTIC, T2).

## Sources

1. Tom Capper, correlation-vs-causation filter (via syntheses/seo.md) | tier 1 | 2026-08-14
2. Kevin Indig, AI citation decoupling + presence/portability/concentration | growth-memo.com | tier 1 | 2026-08-15
3. Ryan Law / Guan, AI Overviews reduce clicks (−34.5%) | ahrefs.com/blog/ai-overviews-reduce-clicks | tier 1 | 2026-08-15
4. Aleyda Solis, AI search aggregation + checklist | aleydasolis.com | tier 1 | 2026-08-15
5. Tim Soulo / Josh Dunning, traffic-potential + bottom-funnel intent (via syntheses/seo.md) | tier 1 | 2026-08-14
6. Syntheses: practitioner-intelligence/syntheses/seo.md, aeo.md, channels-longtail.md | tier 1 | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Dataset | Rankings only | Features noted | Feature-level data stored for tracking |
| Intent | Guessed | Classified | Verified against live top results |
| Opportunity | Gut-ranked | Scored | Tiered with feature targets and owners |
| Actionability | "write better content" | Structural tips | Page-level briefs + cannibalization decisions |
| Iteration | One-off | Periodic pulls | Attribution loop with win/loss tracking |

### Common Failure Modes
- Judging opportunity by search volume instead of the actual SERP layout
- Assuming a #1 rank means full visibility — features can compress or steal the click
- Chasing snippets on keywords whose intent doesn't match your page type
- Ignoring cannibalization while writing more overlapping content
- Treating AI Overview citations as separate from classic SERP analysis
- Pulling SERPs once and never re-measuring — landscapes shift quarterly
