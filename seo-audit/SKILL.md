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

## Practitioner Grounding & Decision Rules

Built from the SEO canon: Glenn Gabe (core-update forensics), Lily Ray (algorithm + content quality), Patrick Stox (technical/enterprise), John Mueller (Google), Will Critchlow (controlled SEO testing), Aleyda Solis, Jamie Indigo, Tom Capper (correlation discipline), Tim Soulo (traffic potential), Sam Dunning (bottom-funnel SaaS SEO), Kevin Indig (programmatic + AI search), Koray Gübür (topical authority, T3 for linkless claims), Paddy Moogan (links), Joy Hawkins (local). Full research: practitioner-intelligence/syntheses/seo.md.

- **Diagnose before acting on drops** (Gabe/Ray — EMPIRICAL, T1): classify a traffic drop as relevancy adjustment / intent shift / quality problem before touching content. Never nuke content until the cause is known.
- **Indexing and crawl gate everything** (Stox/Mueller — FACT, T1): crawl/index issues come first; manage perceived inventory (params, orphans, soft 404s), ignore crawl-budget noise.
- **Ship 5-10 prioritized fixes, never a findings dump** (Stox/Solis/Indigo — FRAMEWORK, T1): three independent practitioners, identical rule. Impact × effort matrix; drop low-impact/high-effort.
- **Quality-driven core-update recovery is a long game** (Gabe/Ray — EMPIRICAL, T1): remediation lands at the next update, often several; kitchen-sink remediation, no short-term testing, no cherry-picking.
- **Ranking-factor claims are hypotheses** (Capper/Critchlow — EMPIRICAL, T1): expert prediction of change outcomes ≈ chance; treat tool correlations as hypotheses, not facts.
- **Volume is a trap** (Soulo/Dunning/Law — EMPIRICAL, T1): filter by traffic potential and bottom-funnel intent, not search volume.

Decision rules:
1. IF traffic drops THEN produce a delta report (GSC pre/post) and classify the cause (relevancy / intent / quality) BEFORE any remediation (Gabe — EMPIRICAL, T1).
2. IF the drop classifies as site quality THEN plan kitchen-sink remediation with the expectation of recovery at the next core update, often several — and refuse short-term testing or cherry-picked fixes (Gabe/Ray — EMPIRICAL, T1).
3. IF launching or migrating THEN audit index coverage and rendering parity before judging rankings (Indigo — FRAMEWORK, T1).
4. IF prioritizing technical fixes THEN score impact × effort and ship 5-10 dev tickets with acceptance criteria — a findings dump is a failed audit (Stox/Solis — FRAMEWORK, T1).
5. IF evaluating a ranking-factor claim THEN apply Capper's four-explanation filter (causation / reverse causation / confounding / coincidence) before acting on it (Capper — FRAMEWORK, T1).
6. IF keyword selection is volume-first THEN re-filter: traffic potential (Soulo) and bottom-funnel intent (Dunning) first; high-volume keywords that convert no one are a trap (Soulo/Dunning — EMPIRICAL, T1).
7. IF considering a template-level change (titles, boilerplate, headers) on 100+ similar pages THEN test it with a control group first — untested best-practice rollouts have documented −27% outcomes (Critchlow — EMPIRICAL, T1).
8. IF content decays (traffic declining without ranking loss) THEN refresh or prune on a schedule — publish-and-forget is a treadmill (Indig — EMPIRICAL, T1).

## Metrics

- **Primary (stage-dependent)**: demos/revenue attributed to organic (B2B), conversions (commerce); rankings are diagnostic, not the goal (Dunning/Law — EMPIRICAL, T1).
- **Index coverage** and core-update volatility exposure (GSC) — the health layer.
- **AI citation share** where the vertical is AI-sensitive (Indig — HYPOTHESIS, T2): classic SERP #1 can have zero AI citations — track both surfaces.
- **Referring domains from earned sources** (links layer).
- **Audit output quality**: % of findings that become shipped fixes (Stox — FRAMEWORK, T1).

## Practitioner-Sourced Failure Modes

- Mass templated content without a uniqueness floor → scaled-content enforcement collapse (2024-26 cases; Ray; Indig — EMPIRICAL, T1).
- Untested best-practice rollouts (Critchlow −27% title-tag incident — EMPIRICAL, T1).
- Checklist-dump audits with no goal linkage — they sit in folders (Stox/Solis — HEURISTIC, T1).
- Single-cause attribution of traffic drops (Gabe — EMPIRICAL, T1).
- Crawl-budget obsession — mostly noise vs inventory management (Mueller/Stox — FACT, T1).

## Sources

1. Glenn Gabe, core-update taxonomy + kitchen-sink FAQ | gsqi.com | tier 1 | 2026-08-14
2. Patrick Stox, enterprise SEO audit + governance | patrickstox.com | tier 1 | 2026-08-14
3. John Mueller / Google, crawl budget docs | developers.google.com | tier 1 | 2026-08-14
4. Will Critchlow, SEO testing + negative tests (SearchPilot) | voicesofsearch.com / searchpilot.com | tier 1 | 2026-08-14
5. Tim Soulo, traffic potential vs volume | Ahrefs blog | tier 1 | 2026-08-14
6. Sam Dunning, 90-day SaaS SEO strategy + mistakes | linkedin.com/in/samdunning | tier 1 | 2026-08-14
7. Kevin Indig, programmatic SEO + AI search studies | kevinindig.com | tier 2 | 2026-08-14
8. Koray Gübür, topical authority (linkless-claims T3) | holisticseo.digital | tier 2/3 | 2026-08-14
9. Tom Capper, correlation taxonomy | Moz | tier 1 | 2026-08-14
10. Lily Ray, algorithm + scaled-content enforcement analysis | lilyray.tech | tier 1 | 2026-08-14

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