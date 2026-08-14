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

## Practitioner Grounding & Decision Rules

Built from Patrick Stox (Ahrefs), John Mueller (Google), Jamie Indigo, Aleyda Solis, Will Critchlow (SearchPilot), Kevin Indig. Full research: practitioner-intelligence/syntheses/seo.md.

- **Index/crawl first, then on-page, then links** (Stox/Mueller — FACT/HEURISTIC, T1): crawl/index issues gate everything downstream. Mueller: perceived inventory (params, orphans, soft 404s) is the only strongly controllable crawl factor; crawl-budget tuning beyond inventory management is mostly noise.
- **Templates, not pages** (Stox — FRAMEWORK, T1): at enterprise scale, fix template-level problems (CMS, rendering, canonical logic) — page-level fixes don't scale.
- **Test template-level changes with controls** (Critchlow — EMPIRICAL, T1): SEOs predict change outcomes ≈ chance; documented −27% from an untested title-tag rollout and a negative from boilerplate removal. When 100+ similar pages share a template, A/B test the change on a subset first.
- **Governance is the deliverable** (Stox/Indigo — FRAMEWORK, T1): technical SEO only persists with launch-lifecycle requirements, regression checks, and owner assignments.

Decision rules:
1. IF a page or template isn't indexing THEN diagnose inventory first (params, orphans, soft 404s, canonical logic) before anything else — indexing gates all downstream work (Stox/Mueller — FACT, T1).
2. IF the change touches a template shared by 100+ similar pages THEN test it on a control subset first — untested best-practice rollouts have documented negative outcomes (Critchlow — EMPIRICAL, T1).
3. IF fixing issues THEN fix template-level root causes before page-level symptoms; a template fix resolves N pages, a page fix resolves one (Stox — FRAMEWORK, T1).
4. IF prioritizing dev work THEN ship 5-10 impact × effort-scored tickets with acceptance criteria — never a findings dump (Stox/Solis — FRAMEWORK, T1).
5. IF someone proposes crawl-budget tuning beyond inventory management THEN decline unless there's evidence of wasted crawl on meaningful pages (Mueller — FACT, T1).
6. IF a migration or launch is underway THEN audit index coverage and rendering parity before judging results (Indigo — FRAMEWORK, T1).
7. IF no regression check exists for SEO requirements in the release lifecycle THEN add one — technical debt accumulates silently without it (Indigo — FRAMEWORK, T1).

## Metrics

- **Index coverage ratio** (indexed / crawlable) and rendering parity (Indigo — FRAMEWORK, T1).
- **Crawl efficiency**: share of crawl on meaningful pages (params/orphans share) — the only crawl-budget metric that matters (Mueller — FACT, T1).
- **Template defect count** (e.g., % of pages failing canonical/title rules) — the scaling health metric (Stox — FRAMEWORK, T1).
- **Regression rate**: SEO bugs introduced per release cycle (Indigo — FRAMEWORK, T1).

## Practitioner-Sourced Failure Modes

- Untested template rollouts (−27% title-tag incident, boilerplate removal negative — Critchlow, EMPIRICAL, T1).
- Crawl-budget obsession instead of inventory management (Mueller/Stox — FACT, T1).
- Page-level fixes at template scale — nothing ships and nothing compounds (Stox — HEURISTIC, T1).
- Audit findings without owners or acceptance criteria (Stox/Solis — HEURISTIC, T1).

## Sources

1. Patrick Stox, enterprise SEO audit + governance | patrickstox.com | tier 1 | 2026-08-14
2. John Mueller / Google, crawl budget documentation | developers.google.com | tier 1 | 2026-08-14
3. Will Critchlow, SEO testing + negative tests (SearchPilot) | voicesofsearch.com | tier 1 | 2026-08-14
4. Jamie Indigo, technical SEO + site architecture | their technical writing | tier 2 | 2026-08-14
5. Aleyda Solis, technical SEO audits | Orainti | tier 1 | 2026-08-14
6. Kevin Indig, technical hygiene as update insurance | kevinindig.com | tier 2 | 2026-08-14

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
