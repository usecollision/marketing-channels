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
