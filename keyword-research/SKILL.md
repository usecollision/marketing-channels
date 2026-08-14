---
name: keyword-research
category: seo
description: Systematic keyword research for topical authority, content planning, and search visibility.
triggers:
  - "keyword research"
  - "what should we rank for"
  - "keyword strategy"
  - "topical authority"
  - "content keywords"
inputs:
  - product_context
  - seed_keywords
  - competitor_urls
outputs:
  - keyword_map
  - topical_clusters
  - content_plan
  - priority_keywords
related_skills:
  - seo-audit
  - site-architecture
  - marketing-messaging/content-strategy
  - marketing-channels/ai-search-audit
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
  - mcp:semrush
  - mcp:ahrefs
version: 1.0.0
---

## When to Use

Invoke when:
- Starting an SEO/content strategy from scratch
- Expanding into new topic areas
- Planning a content calendar based on search demand
- Identifying quick-win keyword opportunities
- Building topical authority architecture

## Workflow

### Step 1: Seed Keyword Generation
Start with broad seeds from multiple angles:
- Product features and use cases
- Customer pain points and questions (from research)
- Competitor top-ranking keywords
- Industry terms and jargon
- Job-to-be-done phrases
- Alternative/comparison queries

**Gate:** 20+ seed keywords across different intent types.

### Step 2: Keyword Expansion
For each seed, expand using:
- Related searches and People Also Ask
- Autocomplete suggestions (A-Z method)
- Competitor keyword gaps (what they rank for, you don't)
- Long-tail variations and questions
- Modifier patterns (best, how to, vs, alternative, for [use case])

Organize by intent:
| Intent Type | Keywords | Search Volume | Difficulty | Funnel Stage |
|-------------|----------|---------------|------------|-------------|
| Informational | how to... | | | Awareness |
| Commercial | best [category] | | | Consideration |
| Transactional | [product] pricing | | | Decision |
| Navigational | [brand] login | | | Retention |

**Gate:** 100+ keywords collected with volume, difficulty, and intent classified.

### Step 3: Topical Cluster Design
Group keywords into topical clusters:

`
Pillar Topic: [broad topic you want to own]
├── Cluster 1: [subtopic]
│   ├── keyword a (volume, KD)
│   ├── keyword b
│   └── keyword c
├── Cluster 2: [subtopic]
│   ├── keyword d
│   └── keyword e
└── Cluster 3: [subtopic]
    ├── keyword f
    └── keyword g
`

Each cluster = one pillar page + 5-10 supporting pages, all interlinked.

**Gate:** 3-5 topical clusters defined with clear pillar/support hierarchy.

### Step 4: Prioritization
Score keywords for priority:

| Keyword | Volume | Difficulty | Business Value | Current Position | Priority |
|---------|--------|------------|---------------|-----------------|----------|

Scoring formula: Priority = (Volume x Business Value) / Difficulty

Categories:
- **Quick wins:** Already ranking 11-30, low difficulty, decent volume
- **Strategic bets:** High volume, high difficulty, high business value (long-term)
- **Low-hanging fruit:** Low difficulty, moderate volume, good fit

**Gate:** Top 20 priority keywords identified with clear rationale and timeline.

### Step 5: Content Map
Map keywords to content assets:

| Keyword Cluster | Content Type | URL | Status | Priority |
|----------------|--------------|-----|--------|----------|
| [cluster] | Pillar guide | /guide/[topic] | To create | P0 |
| [keyword] | Blog post | /blog/[slug] | To create | P1 |
| [keyword] | Landing page | /[category] | Exists, optimize | P0 |

**Gate:** Every priority keyword has an assigned content piece with format and URL.

## Practitioner Grounding & Decision Rules

Built from Tim Soulo (Ahrefs — traffic potential), Sam Dunning (bottom-funnel SaaS SEO), Ryan Law (audience-first content), Koray Gübür (topical authority, T3 for linkless claims), Eli Schwartz (product-led SEO), Kevin Indig. Full research: practitioner-intelligence/syntheses/seo.md.

- **Search volume is a trap; traffic potential is the real filter** (Soulo — EMPIRICAL, T1): a keyword's volume ≠ its ability to deliver traffic you can capture. Filter by ranking difficulty × intent × business fit (traffic potential), then volume.
- **Bottom-funnel intent over volume** (Dunning — EMPIRICAL, T1): for B2B/SaaS, demo-intent and buyer-language keywords beat informational volume; "volume" keywords that convert no one are the #1 observed mistake.
- **The query decides the format** (Dean 2.0/E. Schwartz — FRAMEWORK, T1): neither depth nor brevity is universally right — the SERP and intent decide. Gübür's topical depth wins in competitive informational niches without link equity; Law's brevity wins where buyers don't search generic topics (DISAGREEMENT with conditions).
- **Product-led SEO** (E. Schwartz — FRAMEWORK, T1): if the product can serve bottom-funnel queries (comparison pages, tools, data), build the searchable asset — links follow.

Decision rules:
1. IF a keyword has high volume but low traffic potential (can't rank, no intent match, no business fit) THEN drop it regardless of volume (Soulo — EMPIRICAL, T1).
2. IF the business is B2B/SaaS with demos as the KPI THEN filter for bottom-funnel/buyer-language intent FIRST, then volume (Dunning — EMPIRICAL, T1).
3. IF the niche is competitive-informational and link equity is low THEN use exhaustive topical coverage (Gübür — condition); IF buyers don't search generic topics THEN use audience-pain selection and brevity (Law — condition) — never both blindly (DISAGREEMENT, T1/T2).
4. IF the product can answer queries directly (tools, comparisons, data) THEN prioritize product-surface pages before content pages (E. Schwartz — FRAMEWORK, T1).
5. IF the SERP shows a format (video, listicle, tool, short answer) THEN match it — the query decides the format, not the writer (Dean 2.0 — FRAMEWORK, T1).
6. IF building a topic cluster THEN verify each page's unique intent and traffic potential before writing — cluster pages without individual intent are content for content's sake (Soulo/Law — EMPIRICAL, T1).

## Metrics

- **Traffic potential** (rank-ability × intent match × business fit) per keyword — the selection metric (Soulo — EMPIRICAL, T1).
- **Demos/conversions attributed to target keywords** — not rankings (Dunning — EMPIRICAL, T1).
- **Cluster health**: % of cluster pages with real impressions and engagement (Law — HEURISTIC, T2).

## Practitioner-Sourced Failure Modes

- Volume-first selection — "high-volume keywords that convert no one" (Soulo/Dunning — EMPIRICAL, T1).
- Content written for topics buyers don't search (Law — HEURISTIC, T1).
- Cluster pages without individual intent — duplicate-ish content that dilutes the cluster (synthesis — HEURISTIC, T2).
- Chasing volume in competitive niches without link equity — pages never rank (Gübür's condition, T3).

## Sources

1. Tim Soulo, traffic potential vs volume | Ahrefs blog | tier 1 | 2026-08-14
2. Sam Dunning, 90-day SaaS SEO strategy + mistake lists | linkedin.com/in/samdunning | tier 1 | 2026-08-14
3. Ryan Law, audience-first content strategy | Animalz | tier 2 | 2026-08-14
4. Koray Gübür, topical authority methodology (linkless claims T3) | holisticseo.digital | tier 2/3 | 2026-08-14
5. Eli Schwartz, *Product-Led SEO* | tier 2 | 2026-08-14
6. Kevin Indig, keyword research + content strategy essays | kevinindig.com | tier 2 | 2026-08-14

## Evaluation & QA

### Common Failure Modes
- Targeting only high-volume keywords (impossible to rank for at early stage)
- Ignoring search intent (ranking for informational when you need transactional)
- No topical clustering (random posts without authority building)
- Not considering business value (traffic without conversion potential)
- Skipping competitor analysis (reinventing the wheel)