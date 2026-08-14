---
name: ai-search-audit
category: ai-search
description: Audit your brand visibility across AI search surfaces - ChatGPT, Perplexity, Claude, Gemini, and Copilot.
triggers:
  - "AI search audit"
  - "AEO audit"
  - "GEO audit"
  - "AI visibility"
  - "are we showing up in ChatGPT"
  - "AI discoverability"
  - "LLMO"
inputs:
  - product_context
  - brand_name
  - target_queries
  - competitor_names
outputs:
  - visibility_report
  - citation_analysis
  - gap_recommendations
  - entity_health_score
related_skills:
  - entity-optimization
  - citation-strategy
  - marketing-channels/seo-audit
  - marketing-messaging/content-strategy
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
  - mcp:ai-query
version: 1.0.0
---

## When to Use

Invoke when:
- Want to understand how AI assistants describe/recommend your product
- Competitors are being cited in AI responses but you aren't
- Planning an AI search optimization strategy
- Measuring ROI of content and SEO efforts on AI visibility
- After major content or positioning changes

## Workflow

### Step 1: Query Design
Build a query set that mirrors how your ICP asks AI assistants:

**Query categories:**
- Brand queries: "What is [brand]?" "Tell me about [brand]"
- Category queries: "Best [category] tools" "Top [solution type]"
- Problem queries: "How do I [solve problem]?" "[Pain point] solution"
- Comparison queries: "[Brand] vs [competitor]" "Alternative to [competitor]"
- Recommendation queries: "What [tool/service] should I use for [use case]?"

Build 20-30 queries across all categories.

**Gate:** Query set covers brand, category, problem, comparison, and recommendation intents.

### Step 2: Multi-Surface Testing
Test each query across all major AI surfaces:

| Query | ChatGPT | Perplexity | Claude | Gemini | Copilot |
|-------|---------|-----------|--------|--------|---------|
| [query] | Mentioned? Position? Cited? | ... | ... | ... | ... |

For each response, record:
- **Mentioned:** Is your brand mentioned at all? (Y/N)
- **Position:** Where in the response? (1st, 2nd, 3rd, etc.)
- **Sentiment:** Positive, neutral, or negative framing?
- **Accuracy:** Is the information about you correct?
- **Citation:** Is your website cited as a source?
- **Recommendation:** Are you recommended as a solution?

**Gate:** All queries tested across 3+ AI surfaces with structured data.

### Step 3: Competitor Benchmarking
Compare your visibility to competitors:

| Metric | You | Comp A | Comp B | Comp C |
|--------|-----|--------|--------|--------|
| Brand mention rate | X% | | | |
| Category presence | X/20 | | | |
| Recommendation rate | X% | | | |
| Citation rate | X% | | | |
| Average position | X | | | |
| Sentiment score | X | | | |

**Gate:** Clear picture of where you stand vs competitors in AI search.

### Step 4: Gap Analysis
Identify specific gaps:

**Not mentioned at all:**
- Which queries completely miss you?
- What do AI surfaces say instead?
- What sources are they citing?

**Mentioned but not recommended:**
- What language do they use about you?
- What would make them recommend you?
- What signals are competitors providing that you aren't?

**Inaccurate information:**
- What's wrong? (pricing, features, positioning)
- Where is the wrong info likely coming from?
- How to correct it?

**Gate:** Specific, actionable gaps identified with root cause analysis.

### Step 5: Optimization Roadmap
Build action plan to improve AI visibility:

| Action | Impact | Effort | Timeline |
|--------|--------|--------|----------|
| Fix inaccurate entity data | High | Low | Week 1 |
| Create comparison content | High | Medium | Week 2-3 |
| Improve schema/structured data | Medium | Low | Week 1 |
| Build citation-worthy resources | High | High | Month 2 |
| PR and third-party mentions | High | High | Ongoing |

**Gate:** Prioritized roadmap with specific actions and expected outcomes.

## Practitioner Grounding & Decision Rules

Built from Kevin Indig (3.7M-citation study), the Stanford GEO group (Aggarwal et al., KDD 2024 + GEO-Bench 2026), Andy Crestodina (Orbit Media), Aleyda Solis, Ryan Law/Ahrefs (1.4M-prompt study). Full research: practitioner-intelligence/syntheses/aeo.md.

- **Rank first, get cited second** (Law/Linehan/Guan — EMPIRICAL, T1): ~88% of ChatGPT's cited URLs come from its search-retrieval channel. If you don't rank for the seed query, no GEO spend helps — fix SEO/crawlability first. This is the audit's prerequisite gate.
- **Never use one blended AI-visibility score** (Indig — EMPIRICAL, T1): only 2.37% of cited URLs appear in all three engines; 91% appear in exactly one. Measure Presence (cited anywhere), Portability (cited in 2+ engines), Concentration (single-engine dependence) separately. A "strong aggregate" can mean invisible in 2 of 3 engines.
- **Treat each AI answer as a sample, not a ranking** (Solis — HEURISTIC, T2): aggregate at topic level across runs before deciding anything.
- **Schema alone does not move citations** (Ahrefs controlled test of 1,885 pages — EMPIRICAL, T1): JSON-LD addition → null result (AIO −4.6%, AI Mode +2.4%, ChatGPT +2.2%). Schema is a content-planning lens, not a quick lever.
- **AIO answers ≠ traffic** (Law/Walsh — EMPIRICAL/OPINION, T1): plan for value-based clicks and brand-query lift, not CTR, where AI Overviews cover queries.

Decision rules:
1. IF the brand doesn't rank in classic search for the topic THEN do not start GEO work — fix ranking/crawlability first; ~88% of citations come from search retrieval (Law — EMPIRICAL, T1).
2. IF measuring AI visibility THEN track Presence / Portability / Concentration per engine-topic cell, never a blended score (Indig — EMPIRICAL, T1).
3. IF an answer run shows a mention THEN re-run at topic level before treating it as signal — single answers are samples (Solis — HEURISTIC, T2).
4. IF considering schema as a citation fix THEN don't — measured null; use schema as a content-planning lens instead (Ahrefs — EMPIRICAL, T1).
5. IF AI Overviews cover the query THEN reset expectations: position-1 CTR drops ~34.5% in AIO presence; measure brand-query GSC lift and value-based clicks instead (Law/Guan — EMPIRICAL, T1).
6. IF building the prompt library THEN source it from transcripts/reviews/community language, not keyword tools (Solis — HEURISTIC, T2).
7. IF comparing engines THEN expect low overlap — portability, not aggregate rank, is the goal (Indig — EMPIRICAL, T1).

## Metrics

- **Presence / Portability / Concentration** per topic (Indig — EMPIRICAL, T1).
- **Own-domain vs third-party citation ratio** — ~85% of AI brand citations come from third-party domains (Crestodina — EMPIRICAL, T1).
- **Brand-query GSC lift** — the conversion-side signal when AIOs cover the query (Law — EMPIRICAL, T1).
- **Citation decay monitoring** — refresh quarterly for news/trending; evergreen entity pages persist (Crestodina ~13 weeks vs Indig — DISAGREEMENT, T2).

## Practitioner-Sourced Failure Modes

- Schema-only "optimization" — measured null; the field's most common wasted effort (Ahrefs — EMPIRICAL, T1).
- Blended scores masking single-engine concentration (Indig — EMPIRICAL, T1).
- Binary mentioned/not-mentioned measurement — presence ≠ recommendation ≠ own-domain citation (Solis — HEURISTIC, T2).
- Treating AI search as an external event instead of a strategic variable (Walsh — HEURISTIC, T2).
- JS-rendered content invisible to LLM crawlers (Law/Solis — EMPIRICAL, T2).

## Sources

1. Aggarwal et al., "Generative Engine Optimization" (KDD 2024) | arxiv.org/abs/2311.09735 | tier 1 | 2026-08-15
2. GEO-Bench, adversarial manipulation benchmark (2026) | arxiv.org | tier 1 | 2026-08-15
3. Kevin Indig, "The Consensus Gap" (3.7M citations study) | growth-memo.com | tier 1 | 2026-08-15
4. Ahrefs, "Why ChatGPT Cites Pages" (1.4M prompts) | ahrefs.com/blog/why-chatgpt-cites-pages | tier 1 | 2026-08-15
5. Ahrefs, schema/AI-citation controlled experiment (1,885 pages) | ahrefs.com/blog/schema-ai-citations | tier 1 | 2026-08-15
6. Ahrefs, "AI Overviews Reduce Clicks" (−34.5% position-1 CTR) | ahrefs.com/blog/ai-overviews-reduce-clicks | tier 1 | 2026-08-15
7. Ahrefs, most-cited domains on Perplexity | ahrefs.com/blog/most-cited-domains-perplexity | tier 1 | 2026-08-15
8. Andy Crestodina, "What SEOs Get Wrong About AI Search" | orbitmedia.com | tier 1 | 2026-08-15

## Evaluation & QA

### AI Search Visibility Score
| Component | Weight | Score (0-100) |
|-----------|--------|---------------|
| Brand recognition (AI knows you exist) | 20% | |
| Category association (listed in your category) | 20% | |
| Recommendation rate (actively suggested) | 25% | |
| Citation rate (your site as source) | 20% | |
| Information accuracy | 15% | |
| **Weighted Total** | | |

### Common Failure Modes
- Testing only one AI surface (they have different training data)
- Not testing from competitor perspective (comparison queries)
- Ignoring information accuracy (wrong info = worse than no mention)
- Expecting quick fixes (AI training data updates slowly)
- Not creating citation-worthy content (AI cites authoritative sources)