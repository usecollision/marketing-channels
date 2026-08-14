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

## Practitioner Grounding & Decision Rules

Built from Aleyda Solis (International SEO process + hreflang tooling), Google hreflang documentation, seoClarity hreflang failure data, Search Engine Land international guide, plus the SEO synthesis. Full research: practitioner-intelligence/syntheses/channels-longtail.md.

- **Process before architecture** (Solis — FRAMEWORK, T2): assess international potential (local-language demand) → target audience → architecture → localization → measure per market. Demand is sized in the local language, never translated global volume.
- **Architecture is a long-term commitment** (Solis/SEL — HEURISTIC, T2): subdirectory on one domain is the default; ccTLD only for legal, trust, or local-partner reasons; one URL pattern per language-market pair; never IP-based auto-redirect.
- **Hreflang must be complete and validated** (Google docs — FACT, T1): one mechanism, bidirectional + self-referencing tags, x-default for uncovered locales, correct ISO codes (en-us, not en); failures compound silently (seoClarity: 20-300% impression lifts when fixed — vendor T3; validate with GSC after every deploy).
- **Translate intent, not words** (Solis/SEL — HEURISTIC, T1/T2): machine translation unsupervised fails; near-identical locale pages can't rank independently — material localization or don't publish.
- **Equivalence via hreflang, never rel=canonical** (Google docs — FACT, T1): canonicalizing across locales collapses all regional rankings into one.

Decision rules:
1. IF expanding to a market THEN size search demand in the local language and map local competitors before any architecture work (Solis — FRAMEWORK, T2).
2. IF choosing structure THEN default to subdirectory on one domain; ccTLD only when legal/trust/local-partner reasons justify authority split (Solis/SEL — HEURISTIC, T2).
3. IF a locale page would be near-identical to another market's version THEN localize it materially (copy, pricing, proof, examples) or don't publish (SEL — HEURISTIC, T1/T2).
4. IF deploying hreflang THEN use one mechanism only, with bidirectional + self-referencing tags + x-default, and validate with GSC after every deploy (Google docs — FACT, T1).
5. IF localization budget is thin THEN prioritize by demand×fit and go deep on fewer markets rather than shallow on many (Solis — HEURISTIC, T2).
6. IF a locale cluster shows crawl waste or thin indexation THEN prune or consolidate it at the quarterly market review (synthesis — HEURISTIC, T2).

## Metrics

- **Per-market organic demand** — local-language traffic, rankings, and indexation per locale cluster (Solis — FRAMEWORK, T2).
- **Hreflang validation pass rate** — zero missing reciprocal/self-referencing tags after every deploy; GSC International Targeting report clean (Google docs — FACT, T1).
- **Localization depth compliance** — share of locale pages meeting the material-localization bar (SEL — HEURISTIC, T2).
- **Crawl waste per locale** — near-duplicate pages inflating crawl (synthesis — HEURISTIC, T2).
- Guardrail: no IP-based redirect incidents; no cross-locale rel=canonical usage.
- Re-measure: after every deploy (hreflang); quarterly per-market reviews (prune thin locales, re-prioritize demand).

## Practitioner-Sourced Failure Modes

- Auto-redirecting users by IP instead of respecting hreflang and URL choice (Google docs — FACT, T1).
- Machine-translating keywords and copy unsupervised — reads as spam, ranks nowhere (SEL — HEURISTIC, T2).
- Using rel=canonical across locales — collapses all regional rankings into one (Google docs — FACT, T1).
- Near-identical locale pages competing with each other and wasting crawl budget (SEL — HEURISTIC, T1/T2).
- Missing return links, self-referencing failures, orphaned hreflang configs — targeting breaks down globally (seoClarity — EMPIRICAL, T3).
- Forgetting x-default — uncovered users hit the wrong locale (Google docs — FACT, T1).
- Treating localization as a one-time translation project instead of an ongoing pipeline (Solis — HEURISTIC, T2).

## Sources

1. Aleyda Solis, International SEO Checklist + hreflang tags generator | moz.com/blog/the-international-seo-checklist; aleydasolis.com | tier 1 | 2026-08-15
2. Google, hreflang documentation | developers.google.com/search/docs | tier 1 (FACT) | 2026-08-15
3. seoClarity, 11 Common Hreflang Mistakes (20-300% lift claim) | seoclarity.net | tier 3 | 2026-08-15
4. Search Engine Land, International SEO: Measure Results & Avoid Costly Mistakes | searchengineland.com | tier 2 | 2026-08-15
5. Synthesis: practitioner-intelligence/syntheses/seo.md, channels-longtail.md | tier 1 | 2026-08-15

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
