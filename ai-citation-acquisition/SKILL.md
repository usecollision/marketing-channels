---
name: ai-citation-acquisition
category: ai-search
description: Earn citations in the sources AI engines quote - Wikipedia, reports, review sites, and primary data.
triggers:
  - "get cited by ChatGPT"
  - "AI citation"
  - "get in Wikipedia"
  - "become a primary source"
  - "earn citations"
  - "citation-worthy content"
  - "data study"
  - "get referenced by AI"
inputs:
  - brand_name
  - target_queries
  - existing_assets
  - proprietary_data
  - subject_matter_experts
outputs:
  - citation_target_list
  - citation_worthy_asset_plan
  - wikipedia_strategy
  - data_study_brief
  - outreach_sequence
related_skills:
  - ai-search-audit
  - ai-answer-tracking
  - entity-optimization
  - pr-strategy
  - link-building
  - marketing-messaging/thought-leadership
  - marketing-intelligence/review-mining
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Your brand is absent from the sources AI engines cite while competitors appear
- An AI visibility audit shows mentions but no citations back to your content
- You hold proprietary data (usage patterns, benchmarks, surveys) that no one else has
- You want to become the named primary source AI answers point to in your category
- Planning a data study, industry report, or original research to earn references
- Targeting Wikipedia and other high-authority reference sources for brand mentions

## Workflow

### Step 1: Map What AI Engines Actually Cite
Identify the sources AI engines quote for your target queries:

- [ ] Run your target query set through the AI engines (or reuse the ai-search-audit output) and record every cited source
- [ ] Cluster the cited sources by type - Wikipedia, industry reports, review/comparison sites, vendor blogs, forums, academic papers
- [ ] For each source, note the citation context - is it quoted as a fact, a definition, a statistic, or a recommendation?
- [ ] Rank sources by how often they appear across engines and queries (citation frequency is a heuristic signal of influence)

**Gate:** A ranked list of the specific pages and domains AI engines quote for your category.

### Step 2: Identify Citation Entry Points
Determine where and how you can realistically enter the citation graph:

- [ ] For each high-frequency source, assess entry feasibility - can you contribute, be listed, or be quoted, and what are the rules?
- [ ] Review/comparison sites - do you qualify for a listing, and does your category have a roundup you should be in?
- [ ] Industry reports - which analysts and publishers produce them, and how do they source vendor data?
- [ ] Wikipedia - do you meet notability, and what would a neutral editor accept as a reliable secondary source?
- [ ] Data aggregators and directories that feed AI training corpora

**Gate:** A target list of specific sources with an entry path and a realistic likelihood for each.

### Step 3: Become a Primary Source
Make your brand the origin of data no one else can provide:

- [ ] Inventory proprietary data you already generate - usage stats, benchmarks, trends, survey responses, anonymized aggregates
- [ ] Pick a data angle that answers a question your category cares about and that competitors do not publish
- [ ] Design a study or report with a clean methodology you can defend (sample, timeframe, definitions) - rigor is what earns re-citation
- [ ] Publish on a stable, crawlable URL with a clear title, date, and author attribution (static, indexable, no paywall)
- [ ] Package the finding in quotable units - a headline stat, a chart, and a one-paragraph summary a writer or AI can lift

**Gate:** At least one original-data asset live at a permanent URL with a defensible methodology and quotable takeaways.

### Step 4: Earn the Citations
Run outreach and contribution to turn assets into references:

- [ ] Publish supporting content that cites your primary data (blog, newsletter, social) so it starts circulating
- [ ] Outreach to the analysts, journalists, and editors who write the reports AI cites - pitch the data, not the product
- [ ] Contribute data or expert commentary to existing roundups and reports rather than asking for a link
- [ ] For Wikipedia, route through the proper channels - propose edits on talk pages, cite independent secondary coverage of your data, never self-promote
- [ ] Get third parties to reference the study (industry media, university coverage, conference talks) - independent citations are the currency AI engines respect

**Gate:** A documented outreach campaign with tracked outcomes - who was pitched, who cited, and where the references now live.

### Step 5: Sustain Citation-Worthy Output
Build a repeatable engine, not a one-off study:

- [ ] Set a cadence for recurring original research (an annual benchmark, a quarterly trend report) so you compound citations
- [ ] Maintain a canonical data hub on your site linking every study, so crawlers and engines find the full body of work
- [ ] Track citations over time (hand off to ai-answer-tracking) to see which assets drive mentions
- [ ] Refresh studies when data goes stale - outdated statistics get dropped by editors and engines alike
- [ ] Update entity data and structured content so the machine-readable picture of your brand stays consistent

**Gate:** A recurring research calendar, a canonical data hub, and a citation-tracking loop wired into measurement.

## Practitioner Grounding & Decision Rules

Built from the Stanford GEO group (controlled lab: quotes/statistics/citations = +30-40% visibility), Andy Crestodina (third-party footprint), Kevin Indig (entity portability), Aleyda Solis (prompt libraries), plus Ahrefs citation-mechanics studies. Full research: practitioner-intelligence/syntheses/aeo.md.

- **Quotes, statistics, and citing reliable sources are the highest-lift measured levers** (Stanford — EMPIRICAL, T1): controlled lab results show +30-40% visibility from these content interventions (up to 37% on Perplexity). Do these before structural rewrites.
- **Third-party footprint drives brand citations** (Crestodina/Ahrefs/Law — EMPIRICAL, T1): ~85% of AI brand citations come from third-party domains. Perplexity's top sources: YouTube 31%, Reddit 14%, Wikipedia 7%. Unlinked brand mentions matter more for LLMs than for Google. Reddit content is pulled at volume but cited only 1.93% of the time — presence on the platform ≠ citation.
- **Rank-first prerequisite** (Law — EMPIRICAL, T1): ~88% of ChatGPT citations come from its search-retrieval channel; acquisition without ranking is dead money.
- **Schema-only fixes are null** (Ahrefs — EMPIRICAL, T1): 1,885-page controlled experiment — JSON-LD addition moved nothing.
- **Manipulation is a risk, not a tactic** (GEO-Bench 2026 — EMPIRICAL, T1): black-box rewriting matches gradient attacks and evades detection on some domains, but engines counter actively and detection research is live.

Decision rules:
1. IF the content lacks quotes, statistics, or citations to reliable sources THEN add them first — the highest-lift measured GEO interventions (Stanford — EMPIRICAL, T1).
2. IF building citation acquisition THEN target third-party surfaces first: Reddit discussions, YouTube, Wikipedia, industry publications, unlinked brand mentions — where ~85% of AI citations originate (Crestodina — EMPIRICAL, T1).
3. IF the brand doesn't rank in classic search THEN fix ranking before citation acquisition (Law — EMPIRICAL, T1).
4. IF planning a schema-only fix THEN skip it — measured null; invest in content interventions (Ahrefs — EMPIRICAL, T1).
5. IF considering GEO manipulation THEN treat it as a time-bomb risk, not a tactic — detection research is active (GEO-Bench — EMPIRICAL, T1).
6. IF evaluating Reddit presence THEN measure citations, not content volume — Reddit is pulled at volume but cited rarely (Ahrefs — EMPIRICAL, T1).
7. IF writing content for AI extraction THEN use answer-first structure with self-contained chunks (question-as-heading + immediate answer) (Crestodina/Solis — HEURISTIC, T2).

## Metrics

- **Citation share by engine** (own-domain + third-party) per topic (Indig/Stanford — EMPIRICAL, T1).
- **Third-party citation ratio** — target growth in external surfaces cited about the brand (Crestodina — EMPIRICAL, T1).
- **Intervention lift**: controlled before/after on quote/statistic/citation additions (Stanford method — EMPIRICAL, T1).
- **Citation decay** — refresh cadence for news/trending content (Crestodina — HEURISTIC, T2).

## Practitioner-Sourced Failure Modes

- Schema-only programs (Ahrefs null result — EMPIRICAL, T1).
- Content that never ranks, then GEO spend on top (Law — EMPIRICAL, T1).
- Gaming attempts — unstable, detected, inverted by engines (GEO-Bench — EMPIRICAL, T1).
- Treating AI citations as a content-marketing afterthought (Walsh — HEURISTIC, T2).

## Sources

1. Aggarwal et al., "Generative Engine Optimization" (KDD 2024) | arxiv.org/abs/2311.09735 | tier 1 | 2026-08-15
2. GEO-Bench (2026) | arxiv.org | tier 1 | 2026-08-15
3. Ahrefs, "Why ChatGPT Cites Pages" | ahrefs.com/blog/why-chatgpt-cites-pages | tier 1 | 2026-08-15
4. Ahrefs, "Most-Cited Domains on Perplexity" | ahrefs.com/blog/most-cited-domains-perplexity | tier 1 | 2026-08-15
5. Andy Crestodina, "What SEOs Get Wrong About AI Search" | orbitmedia.com | tier 1 | 2026-08-15
6. Kevin Indig, "The Consensus Gap" | growth-memo.com | tier 1 | 2026-08-15
7. Aleyda Solis, GEO/AEO frameworks | Orainti | tier 2 | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Source mapping | No data | Sources listed | Ranked by citation frequency |
| Entry points | None identified | Some feasible | Target list with path and likelihood |
| Primary source | No unique data | Data published | Defensible methodology, quotable units |
| Citation earned | None | One or two | Recurring, independently cited |
| Sustainability | One-off | Occasional | Cadence + hub + tracking loop |

### Common Failure Modes
- Pitching your product instead of your data - editors and engines ignore promotional content
- Publishing a study with no methodology, which no credible source will cite
- Editing Wikipedia directly for self-promotion, which gets reverted and damages trust
- Chasing citations without a unique data angle, so there is nothing new to reference
- Putting the study behind a paywall, lead form, or JS-only page that crawlers cannot index
- Measuring links instead of citations - the goal is being quoted as a source, not just linked
