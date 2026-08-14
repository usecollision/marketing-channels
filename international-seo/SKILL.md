---
name: international-seo
category: seo
description: Plan and run international and enterprise SEO - hreflang, multi-region site architecture, and localization at scale.
triggers:
  - "international SEO"
  - "multi-region website"
  - "hreflang"
  - "ccTLD vs subdirectory"
  - "localize our site"
  - "expand to new countries"
  - "enterprise SEO"
  - "language targeting"
inputs:
  - target_markets
  - current_site_architecture
  - language_locale_map
  - product_catalog
  - competitor_international_data
outputs:
  - international_architecture_plan
  - hreflang_implementation_spec
  - international_keyword_matrix
  - localization_prioritization_plan
  - enterprise_seo_governance_model
related_skills:
  - seo-audit
  - technical-seo
  - keyword-research
  - programmatic-seo
  - entity-optimization
  - marketing-messaging/localization
  - marketing-intelligence/market-map
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Expanding an existing site into one or more new countries or languages
- Deciding how to structure multi-region URLs (ccTLD, subdirectory, subdomain, or parameter)
- hreflang tags are missing, conflicting, or returning the wrong language in SERPs
- Duplicate content across locales is suppressing rankings or triggering thin-content flags
- Localized pages rank poorly because keyword research was translated instead of re-researched
- Scaling SEO across a large site portfolio (tens or hundreds of locales) with an enterprise team

## Workflow

### Step 1: Market Prioritization & Demand Mapping
Rank target markets by real demand, not assumption:

- [ ] For each candidate market, size search demand in the local language (local keyword volumes, not translated global volumes)
- [ ] Map the competitive landscape per market - who owns the SERPs today (local incumbents, global players, aggregators)
- [ ] Assess product-market fit and localization cost per market (site, support, payments, compliance)
- [ ] Score and stack-rank markets on demand, competition, fit, and cost (heuristic scoring - no universal formula)

**Gate:** A prioritized list of markets with demand evidence and a go/no-go recommendation for each.

### Step 2: Architecture Decision - ccTLD vs Subdirectory vs Subdomain
Choose the URL structure for each locale:

| Option | Signals | Trade-offs |
|--------|---------|------------|
| ccTLD (example.de) | Strongest geo signal, independent hosting | Separate domains, split authority, higher cost |
| Subdirectory (example.com/de/) | Consolidated authority, one domain | Weaker geo signal, needs hreflang |
| Subdomain (de.example.com) | Some separation | Split authority, rarely the right default |
| Language params (?lang=de) | Almost never correct | Weakest signal, indexation risk |

- [ ] Default to subdirectory on one domain unless a ccTLD is justified by legal, trust, or local-partner reasons (heuristic default - weigh authority consolidation against geo strength)
- [ ] Document the decision and the rationale in an architecture decision record
- [ ] Confirm one URL pattern maps one-to-one to one language-locale pair (never mix, never auto-redirect by IP)

**Gate:** Architecture decision documented per market with one canonical URL pattern per locale.

### Step 3: Hreflang Implementation
Make search engines serve the right locale:

- [ ] Define the full locale matrix - every language-market combination gets its own cluster
- [ ] Implement hreflang via one mechanism only (HTML link tags preferred; XML sitemap as the fallback for scale)
- [ ] Include bidirectional and self-referencing tags in every cluster - every page links every locale version including itself
- [ ] Add an x-default for users whose locale is not covered
- [ ] Use absolute URLs and correct ISO 639-1 language + ISO 3166-1 region codes (en-us, not en-us-url, not en)
- [ ] Validate with GSC International Targeting reports and a hreflang crawler after every deploy

**Gate:** Every locale cluster passes hreflang validation with no missing reciprocal or self-referencing tags.

### Step 4: International Keyword Research & Localization
Translate intent, not words:

- [ ] Research keywords natively in each target language - machine translation produces wrong search terms
- [ ] Use local search engines where dominant (Baidu, Yandex, Naver) and local tools for volume data
- [ ] Map local-language keywords to local-language URLs - one keyword cluster per locale page
- [ ] Distinguish true localization (rewrite for local market) from translation (literal word swap) and specify which each page needs
- [ ] Localize currency, units, dates, examples, social proof, and legal/compliance content - not just words
- [ ] Create a glossary of approved brand and product terminology per language to keep naming consistent

**Gate:** A native-language keyword matrix per locale mapped to URL targets, with localization depth specified per page.

### Step 5: Duplicate-Content & Thin-Content Risk Control
Avoid the biggest international SEO failure:

- [ ] Identify pages where the localized version is near-identical to the source (same language, different market is the highest risk)
- [ ] Decide per page: localize meaningfully, consolidate under one URL, or leave off-market (no auto-generated near-duplicate pages)
- [ ] Set a minimum viable localization bar - a page must differ in substance (copy, pricing, proof, examples), not just boilerplate
- [ ] Use hreflang (not rel=canonical across locales) to signal equivalents - canonicalizing across markets collapses rankings
- [ ] Monitor localized-page indexation and crawl waste in GSC; near-duplicate locales inflate crawl budget

**Gate:** Every published locale page is materially localized or removed; hreflang (not cross-locale canonicals) handles equivalence.

### Step 6: Enterprise SEO Governance & Scale
Make international SEO repeatable across a large organization:

- [ ] Define one owner per locale cluster and a global SEO governance board or operating model
- [ ] Standardize templates, schema, and a content model so new locales launch from a repeatable kit
- [ ] Create a locale launch checklist (architecture, hreflang, glossary, localization, tracking) reused for every new market
- [ ] Centralize measurement - one dashboard tracking organic traffic, rankings, and indexation per locale
- [ ] Schedule quarterly per-market reviews to prune thin locales and re-prioritize demand
- [ ] Wire localization pipelines to content ops so new and updated source content flows to all active locales

**Gate:** A governance model with named owners, a reusable locale-launch kit, and a central per-locale dashboard.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Market prioritization | Guesswork | Demand sourced | Demand + competition + fit scoring |
| Architecture | No documented decision | Decision made | Decision recorded with rationale |
| Hreflang | Missing or broken | Implemented | Validated, reciprocal, x-default set |
| Keyword research | Translated | Native-language | Native + local-engine + URL-mapped |
| Localization depth | Machine-translated | Partly localized | Materially localized per page |
| Scale | One-off | Repeatable kit | Governance + dashboard + cadence |

### Common Failure Modes
- Auto-redirecting users by IP instead of respecting hreflang and URL choice
- Machine-translating keywords and copy, which reads as spam and ranks nowhere
- Using rel=canonical across locales, collapsing all regional rankings into one
- Publishing near-identical locale pages that compete with each other and waste crawl budget
- Forgetting x-default, leaving uncovered users guessing or hitting the wrong locale
- Splitting authority across subdomains or ccTLDs without a deliberate reason
- Treating localization as a one-time translation project instead of an ongoing pipeline
