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

## Evaluation & QA

### Common Failure Modes
- Targeting only high-volume keywords (impossible to rank for at early stage)
- Ignoring search intent (ranking for informational when you need transactional)
- No topical clustering (random posts without authority building)
- Not considering business value (traffic without conversion potential)
- Skipping competitor analysis (reinventing the wheel)