---
name: technical-seo
category: seo
description: Diagnose and fix crawlability, indexation, rendering, Core Web Vitals, crawl budget, and structured data issues.
triggers:
  - "technical SEO"
  - "crawl budget"
  - "Core Web Vitals"
  - "pages not indexed"
  - "JavaScript SEO"
  - "structured data errors"
  - "log file analysis"
  - "indexation dropped"
inputs:
  - website_url
  - crawl_tool_exports
  - search_console_data
  - access_logs
outputs:
  - crawlability_report
  - indexation_audit
  - performance_fix_list
  - schema_recommendations
  - crawl_budget_summary
related_skills:
  - seo-audit
  - keyword-research
  - programmatic-seo
  - serp-analysis
  - marketing-optimize/analytics-setup
  - marketing-optimize/landing-page-optimization
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
- Pages aren't getting indexed, or previously indexed pages are dropping out
- Organic traffic shifted after a migration, redesign, or framework change
- Core Web Vitals are failing in Search Console
- Launching a large site that needs crawl-budget hygiene
- Structured data errors keep appearing in Search Console
- Someone has blamed "crawl budget" or "it's a JavaScript problem" without evidence

## Workflow

### Step 1: Crawl Setup & URL Inventory
Build a complete map of the site before diagnosing anything:
- [ ] Crawl the full site (Screaming Frog / Sitebulb / OnCrawl); enable JavaScript rendering if the site is JS-heavy
- [ ] Count URLs: total discovered, indexable candidates, non-indexable, duplicates, parameter variants
- [ ] Crawl with the mobile user-agent too — Google crawls mobile-first
- [ ] Pull baseline indexation from Search Console (Indexing → Pages) plus sitemap-submitted counts
- [ ] Flag the money pages (conversion-critical) — they get priority in every fix below

**Gate:** URL inventory produced with exact counts and money pages separated out. Every later finding must cite specific URLs, not averages.

### Step 2: Crawlability — Can Bots Reach the Pages?
- [ ] robots.txt: no accidental blocks of important sections; test directives against Google's parser rules
- [ ] XML sitemap(s): submitted in GSC, valid, split above 50k URLs, no orphaned or 404 entries inside
- [ ] HTTP status codes: no 5xx storms; real 404s (not soft 404s); redirect chains under 3 hops
- [ ] Canonicals: self-referencing, exactly one per page, never pointing at noindex or redirect targets
- [ ] Faceted navigation and parameters: consolidate or allow crawl deliberately, not by accident
- [ ] Internal links: every important URL reachable within 3 clicks; list orphan pages (zero internal inlinks)

**Gate:** For every important URL there is a documented path: reachable via internal links, permitted by robots.txt, canonical-clean.

### Step 3: Indexation & Rendering
- [ ] GSC Page Indexing report: bucket every page into "Indexed", "Discovered – currently not indexed", "Crawled – currently not indexed"
- [ ] JavaScript rendering: critical content present in raw HTML, not only after hydration; test with JS disabled
- [ ] Render mode assessment: client-side rendering of money content is an indexation risk; SSR/SSG preferred
- [ ] noindex audit: find accidental noindex leaks (staging configs, CMS templates, dev leftovers)
- [ ] Duplicate and near-duplicate content mapping — duplicates dilute crawl and index
- [ ] Mobile-first parity: mobile DOM carries the same content, meta, and structured data as desktop

**Gate:** Root cause identified for each indexation gap bucket in GSC, with a specific fix attached (render change, canonical consolidation, content upgrade, sitemap/robots change).

### Step 4: Core Web Vitals & Performance
- [ ] Measure field data first (CrUX / GSC CWV report); treat lab scores (Lighthouse) as secondary diagnostics
- [ ] LCP under 2.5s field: identify the LCP element (hero image, font, blocking script), preload critical resources
- [ ] CLS under 0.1: fix shifts — dimension all media, reserve ad slots, avoid late-loading fonts
- [ ] INP under 200ms field (successor to FID): find long tasks, trim heavy third-party scripts
- [ ] Third-party script budget: list every third-party and its cost; remove or defer non-essential ones
- [ ] Image pipeline: responsive srcset, WebP/AVIF, lazy-load below the fold, explicit dimensions

**Gate:** Each failing metric mapped to specific offending pages and resources with fixes; third-party budget documented.

### Step 5: Log-File Analysis & Crawl Budget
- [ ] Obtain raw access logs; filter to Googlebot and Bingbot user agents
- [ ] Match bot requests against the URL inventory: crawled vs never-crawled, high vs low frequency
- [ ] Identify crawl waste: parameter URLs, faceted pages, redirect chains, soft 404s consuming bot time
- [ ] Overlay with indexation: "crawled but not indexed" is usually a quality signal problem, not crawl budget
- [ ] For large sites only (below roughly 10k URLs crawl budget is rarely the constraint — heuristic): track bot requests per day vs URL count

**Gate:** One-page crawl-budget summary: what bots waste time on, which important URLs bots visit least, and the three configuration changes (robots, canonicals, sitemap trimming, redirects) that reduce waste.

### Step 6: Structured Data & Schema
- [ ] Inventory existing schema; validate via Rich Results Test and Schema.org validator
- [ ] Map types to page types: Product, Article, FAQPage, LocalBusiness, Organization, VideoObject, BreadcrumbList
- [ ] Triage errors and warnings in the GSC Enhancements reports
- [ ] Prioritize rich-result-eligible markup; never mark up content that isn't visible on the page (policy risk)
- [ ] Add Organization/Person markup with sameAs identifiers on homepage and author pages to anchor entity signals

**Gate:** Every eligible template has validated schema; GSC enhancement errors are triaged into a fix list.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Evidence | Claims without tool data | Crawl data only | Crawl + GSC + field CWV + log data |
| Indexation | No gap analysis | Buckets listed | Root cause per bucket with fix |
| Rendering | JS ignored | JS noted | Render path verified on money pages |
| Crawl budget | Not analyzed | Logs skimmed | Waste quantified with config fixes |
| Actionability | Generic advice | Some fixes | URL-level fixes with priority and owner |

### Common Failure Modes
- Optimizing lab metrics while field data tells a different story
- Blocking bots with over-aggressive robots.txt to "save" crawl budget
- Diagnosing indexation without checking JavaScript rendering first
- Applying crawl-budget fixes to small sites where content quality is the real lever
- Schema markup that doesn't match visible content
- Canonicalizing parameter URLs without verifying the content is actually identical
