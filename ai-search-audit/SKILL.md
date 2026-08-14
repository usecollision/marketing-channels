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