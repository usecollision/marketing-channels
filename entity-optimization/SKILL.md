---
name: entity-optimization
category: ai-search
description: Build your brand as a machine-readable entity - entity extraction, knowledge graph optimization, and citation acquisition for AI search.
triggers:
  - "entity optimization"
  - "knowledge graph"
  - "AEO"
  - "GEO"
  - "brand entity"
  - "Wikidata"
  - "AI citations"
  - "how do AIs describe us"
inputs:
  - brand_name
  - key_people
  - product_catalog
  - existing_wikidata_or_knowledge_panel_state
outputs:
  - entity_audit
  - knowledge_graph_plan
  - third_party_coverage_list
  - mention_acquisition_plan
  - ai_monitoring_dashboard
related_skills:
  - ai-search-audit
  - serp-analysis
  - technical-seo
  - link-building
  - marketing-messaging/brand-voice
  - marketing-intelligence/review-mining
  - marketing-intelligence/social-listening
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
  - mcp:ai-query
version: 1.0.0
---

## When to Use

Invoke when:
- AI assistants describe your brand incorrectly, incompletely, or not at all
- Your brand has no knowledge panel, Wikidata entry, or consistent entity footprint
- Competitors get cited in AI Overviews and chat answers while you don't
- Facts about your brand conflict across Wikipedia, Crunchbase, and your own site
- You want LLMs to cite you as the answer to category-level questions

## Workflow

### Step 1: Entity Extraction & Baseline Audit
- [ ] Extract the entities your brand depends on: organization, products, people, categories, locations
- [ ] Define the canonical fact sheet per entity: name, type, description, founding, HQ, parent, sameAs identifiers
- [ ] Query AI surfaces and Google: how is each entity described today? Log exact answers and citations
- [ ] Compare machine-readable understanding (schema, Wikidata, knowledge panel) against your canonical facts — list every conflict
- [ ] Map the entity graph: which sources (Wikipedia, Wikidata, Crunchbase, directories) feed the current understanding

**Gate:** Entity audit complete: canonical fact sheet per entity, current AI descriptions logged, and every factual conflict identified.

### Step 2: Knowledge Graph Optimization
- [ ] Wikidata: create or complete the entry with statements + references — notability bar applies, cite real coverage
- [ ] Wikipedia: only pursue if genuinely notable per their guidelines; a failed vanity draft hurts more than it helps
- [ ] Google Knowledge Panel: claim it, suggest edits, and fix wrong facts through the panel itself
- [ ] Schema.org: Organization/Person/Product markup with sameAs links to Wikidata, social profiles, and directories on every relevant page
- [ ] Consistency protocol: every fact (name, dates, category) identical across all properties — conflicts fragment entity confidence

**Gate:** Every entity has an owned, referenced Wikidata entry or a documented reason it can't; schema sameAs links live site-wide.

### Step 3: Authoritative Third-Party Coverage
- [ ] Structured databases: Crunchbase-type business registries, industry associations, standards bodies
- [ ] Trusted publications: founder profiles, expert commentary, coverage in outlets AI models weight
- [ ] Author entities: give key people bios with credentials across the web (personal sites, publisher profiles) — E-E-A-T and entity signals reinforce each other
- [ ] Directories and reviews platforms: consistent category placement reinforces what your brand "is"

**Gate:** Third-party coverage list built and prioritized by likely AI-model influence (trusted, widely crawled sources first).

### Step 4: Brand Mention & Citation Acquisition
- [ ] Convert unlinked mentions to links — they anchor the entity across the graph
- [ ] Get cited in the source types AI engines quote: definitions, statistics, comparisons, lists, roundups
- [ ] Digital PR for data and definitions: publish the number or definition others will cite, then make it easy to cite (clear sourcing, quotable phrasing)
- [ ] Keep the cited facts stable and consistent everywhere — AI engines repeat what's corroborated across sources
- [ ] Coordinate with link-building: entity coverage and authority links are two sides of one program

**Gate:** Mention-to-citation pipeline running; at least one quotable asset (stat, definition, study) shipped for citation acquisition.

### Step 5: Answer-Format Optimization (GEO)
- [ ] Audit your content for quotability: definitional first sentences, statistic blocks with sourcing, comparison tables, direct FAQ answers
- [ ] Rewrite key pages so a model can lift a complete, self-contained answer in one paragraph
- [ ] Add citation-friendly elements: named data points, "according to [Brand] research", clear claims with evidence
- [ ] Verify alignment: re-query AIs on your core topics — if they paraphrase you inaccurately, your content is ambiguous or conflicting
- [ ] Publish answers to the exact questions AIs currently answer with competitor sources

**Gate:** Top-priority pages rewritten to quotable format; pre/post AI answer comparison documented.

### Step 6: Monitoring Loop
- [ ] Re-run the audit on a cadence (monthly for core entities — heuristic): AI answers, knowledge panel state, new citations
- [ ] Track share of citation vs competitors on your category questions
- [ ] Log entity-confidence movement: more sources, more consistent facts, better AI descriptions
- [ ] Feed gaps back: content briefs, PR targets, schema fixes, new Wikidata statements

**Gate:** Monitoring dashboard live with citation share, description drift, and entity-confidence trend per quarter.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Entity baseline | No fact sheet | Facts listed | Canonical facts + conflicts logged |
| KG foundation | No Wikidata/KP work | Partial | Referenced Wikidata + claimed KP + sameAs |
| Coverage | Random mentions | Some third-party | Prioritized trusted-source plan |
| Citations | Unlinked mentions | Links acquired | Quotable assets feeding AI citations |
| Monitoring | One-off check | Periodic | Dashboard with citation share trend |

### Common Failure Modes
- Chasing AI mentions without a knowledge-graph foundation — descriptions stay wrong
- Conflicting facts across properties (different founding dates, names) fragmenting entity confidence
- Trying to force a Wikipedia article without meeting notability — wasted effort, possible reputation damage
- Marking up schema that doesn't match visible content
- Treating AEO/GEO as separate from classic SEO and PR instead of layered on top
- Measuring mentions instead of accurate, consistent machine understanding
