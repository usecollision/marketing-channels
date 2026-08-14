---
name: seo-audit
category: seo
description: Run a comprehensive 5-pillar SEO audit covering technical, on-page, content, authority, and performance.
triggers:
  - "SEO audit"
  - "check our SEO"
  - "why aren't we ranking"
  - "technical SEO"
  - "SEO issues"
  - "site health"
inputs:
  - website_url
  - target_keywords
  - competitor_urls
outputs:
  - audit_report
  - issue_priority_matrix
  - fix_recommendations
  - quick_wins_list
related_skills:
  - keyword-research
  - site-architecture
  - marketing-channels/ai-search-audit
  - marketing-optimize/analytics-setup
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
  - mcp:pagespeed
  - mcp:search-console
version: 1.0.0
---

## When to Use

Invoke when:
- Organic traffic is declining or stagnant
- Launching a new site or after a redesign/migration
- Quarterly SEO health check
- Before a content strategy overhaul
- Competitor is outranking you on key terms

## Workflow

### Step 1: Crawlability & Indexation Audit
Check that search engines can find and index your pages:

- [ ] robots.txt - correct directives, not blocking important pages
- [ ] XML sitemap - exists, submitted, accurate, no errors
- [ ] Indexation coverage - pages indexed vs submitted (GSC)
- [ ] Crawl errors - 404s, 5xx, redirect chains/loops
- [ ] Canonical tags - self-referencing, no conflicts
- [ ] Noindex tags - intentional vs accidental
- [ ] JavaScript rendering - critical content visible without JS
- [ ] Mobile-first indexing - mobile version complete

**Issue format:**
| Issue | Impact (H/M/L) | Evidence | Fix | Priority |
|-------|---------------|----------|-----|----------|

**Gate:** All critical crawlability issues identified with evidence.

### Step 2: Technical SEO Audit
Performance and technical health:

- [ ] Core Web Vitals (LCP < 2.5s, FID < 100ms, CLS < 0.1)
- [ ] Page speed (mobile + desktop scores)
- [ ] HTTPS everywhere (no mixed content)
- [ ] URL structure (clean, descriptive, consistent)
- [ ] Structured data / Schema markup (correct, validated)
- [ ] Hreflang (if international)
- [ ] Internal linking structure (orphan pages, crawl depth)
- [ ] Log file analysis (crawl budget issues)

**Gate:** Technical issues scored by impact on rankings and user experience.

### Step 3: On-Page SEO Audit
Content optimization for target keywords:

- [ ] Title tags - unique, keyword-optimized, <60 chars
- [ ] Meta descriptions - compelling, keyword-included, <155 chars
- [ ] H1 tags - one per page, includes primary keyword
- [ ] Header hierarchy (H2-H6) - logical, keyword-rich
- [ ] Content quality - depth, E-E-A-T signals, freshness
- [ ] Internal links - contextual, descriptive anchor text
- [ ] Image optimization - alt text, file names, compression, WebP
- [ ] URL optimization - short, descriptive, keyword-included

**Gate:** Top 20 pages audited with specific on-page improvement recommendations.

### Step 4: Content & Authority Audit
Content quality and backlink profile:

- [ ] Content gap analysis (what competitors rank for that you don't)
- [ ] Thin/duplicate content identification
- [ ] Content freshness (outdated pages that need updates)
- [ ] Topical authority assessment (depth of coverage)
- [ ] Backlink profile health (toxic links, DR/DA trend)
- [ ] Competitor backlink comparison
- [ ] Link building opportunities (unlinked mentions, broken link targets)

**Gate:** Content gaps and authority gaps identified with specific opportunities.

### Step 5: Priority Matrix & Recommendations
Organize all findings into an action plan:

| Priority | Category | Issue | Impact | Effort | Recommendation |
|----------|----------|-------|--------|--------|----------------|
| P0 | Technical | [issue] | High | Low | [specific fix] |
| P1 | On-page | [issue] | High | Medium | [specific fix] |
| P2 | Content | [issue] | Medium | High | [specific action] |

**Quick wins** (high impact, low effort): Top 5 things to do this week
**Strategic fixes** (high impact, high effort): Next 30-day plan
**Maintenance** (low impact, low effort): Ongoing checklist

**Gate:** Every issue has a specific, actionable fix with estimated impact.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Coverage | 1-2 pillars | 3-4 pillars | All 5 pillars with depth |
| Evidence | Claims without data | Some tool data | GSC/analytics/crawl data for each finding |
| Prioritization | Flat list | Impact noted | Impact x Effort matrix with clear P0/P1/P2 |
| Actionability | Vague suggestions | General recommendations | Specific fixes with implementation steps |
| Quick Wins | Not identified | 1-2 obvious ones | 5+ with estimated impact |

### Common Failure Modes
- Running automated tools without interpreting results in context
- Fixing low-impact issues while ignoring critical ones
- Not considering the business value of pages (prioritize money pages)
- Ignoring content quality in favor of purely technical fixes
- Not benchmarking against competitors