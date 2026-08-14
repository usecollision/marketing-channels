---
name: local-seo
category: seo
description: Optimize local search presence - Google Business Profile, citations, reviews, and local ranking factors.
triggers:
  - "local SEO"
  - "Google Business Profile"
  - "Google My Business"
  - "local rankings"
  - "citations"
  - "local reviews"
  - "map pack"
  - "multi-location SEO"
inputs:
  - business_locations
  - service_areas
  - gbp_access
  - competitor_local_data
outputs:
  - gbp_optimization_plan
  - citation_build_list
  - review_generation_plan
  - local_landing_page_specs
  - local_rank_tracker_setup
related_skills:
  - seo-audit
  - technical-seo
  - entity-optimization
  - marketing-intelligence/review-mining
  - marketing-intelligence/customer-research
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Business serves customers at physical locations or defined service areas
- Competitors dominate the local pack / map results while you don't appear
- GBP profile exists but is stale, unclaimed, or suspended
- NAP (name, address, phone) data is inconsistent across directories
- Review velocity is near zero while competitors accumulate hundreds
- Expanding to new locations and need a repeatable local playbook

## Workflow

### Step 1: Local Entity & GBP Audit
- [ ] Claim and verify every GBP listing; confirm primary owner access
- [ ] Audit current state: categories, hours, attributes, photos, posts, review count and response rate
- [ ] NAP audit: export citations from the major aggregators/directories; diff against the canonical NAP
- [ ] Find duplicate GBP listings and rogue/duplicate directory listings
- [ ] Map competitor local presence: their categories, review counts, citation sources

**Gate:** Complete inventory of every GBP and directory listing with discrepancies flagged against one canonical NAP document.

### Step 2: Google Business Profile Optimization
- [ ] Primary category: the single most accurate one; secondary categories fill out the rest — never spam categories
- [ ] Complete every field: services/products catalog, service area, attributes, amenities, appointment and messaging links
- [ ] Business description: factual, keyword-natural, no promotional fluff
- [ ] Photo cadence: owner photos monthly, real customer-visible shots, geotagged where possible (heuristic cadence)
- [ ] Posts: offers, events, updates — refreshed regularly; stale posts signal an abandoned profile
- [ ] Q&A: seed and answer the real pre-purchase questions customers ask

**Gate:** Profile 100% complete per Google's own completion checklist, with photo and post cadence scheduled.

### Step 3: Citation Building & NAP Consistency
- [ ] Publish the canonical NAP format (exact business name, address, phone formatting) as a shared reference doc
- [ ] Fix or remove every inconsistent listing found in Step 1 — consistency outweighs volume
- [ ] Build core citations: data aggregators first (they feed the network), then industry and local directories
- [ ] Tier the rest: general directories, chamber of commerce, vertical-specific, hyperlocal (heuristic tiering — prioritize by relevance to your customers)
- [ ] Track citations in a sheet: platform, URL, status, NAP match, last verified

**Gate:** Top-tier citations consistent and live; citation tracker maintained with verification dates.

### Step 4: Review Engine
- [ ] Build the ask: automated post-purchase/service request (email, SMS, QR) with a direct review link
- [ ] Volume and velocity goals per location — realistic cadence beats one-off bursts (sustained velocity is a signal; heuristic)
- [ ] Respond to every review — owner responses are a documented ranking/relevance signal; templates for speed, personalization for authenticity
- [ ] Negative review SOP: acknowledge, take it offline, resolve publicly, follow up — never argue
- [ ] Mine review language for keywords and objections; feed to on-page copy and product feedback

**Gate:** Review-ask automation live, response SLA adopted, negative-review SOP written and shared.

### Step 5: On-Site Local Signals
- [ ] One dedicated landing page per location/service-area combination — no doorway-page duplicates
- [ ] LocalBusiness schema with geo coordinates, hours, and sameAs links to the GBP and citations
- [ ] Embedded map plus driving directions on each location page
- [ ] Local content: area guides, project showcases, neighborhood-specific proof (photos, testimonials from local customers)
- [ ] Internal linking from homepage/service pages to location pages, and between sibling locations

**Gate:** Every location has a schema-validated landing page with local proof content and correct internal linking.

### Step 6: Local Ranking Monitoring
- [ ] Track the proximity/relevance/prominence triad per keyword: map-pack rank from a grid of search points across your service area
- [ ] Monitor GBP insights: calls, direction requests, website clicks, photo views per month
- [ ] Re-run the NAP/citation audit quarterly; new inconsistencies always appear after acquisitions or rebrands
- [ ] Compare review velocity against top-3 local competitors monthly
- [ ] Re-audit categories and attributes after any Google feature change or business pivot

**Gate:** Local rank tracker live with grid tracking; monthly local scorecard (rank, calls, reviews, NAP health) owned by one person.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| GBP completeness | Unclaimed or stale | Mostly complete | 100% complete with active cadence |
| NAP consistency | Not audited | Audited, unfixed | Consistent + tracker maintained |
| Reviews | No system | Ask exists | Ask + response SLA + negative SOP |
| On-site signals | No local pages | Basic pages | Schema, local proof, geo content |
| Monitoring | Nothing tracked | Rank checks | Grid tracking + monthly scorecard |

### Common Failure Modes
- Keyword-stuffed business names — a suspension risk, not a strategy
- Fake or incentivized reviews, which violate policy and destroy trust
- Building citation volume while NAP inconsistencies poison the network
- Ignoring GBP Q&A — competitors and spam often answer for you
- Local landing pages that are thin duplicates of each other
- Treating local SEO as set-and-forget; reviews and NAP decay without cadence
