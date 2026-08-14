---
name: pinterest-threads
category: social
description: Run Pinterest and Threads as channels - pin and shopping SEO, Threads posting, cross-posting, and community.
triggers:
  - "Pinterest strategy"
  - "Pinterest SEO"
  - "shopping pins"
  - "Threads strategy"
  - "post on Threads"
  - "cross-post from Instagram"
  - "Pinterest or Threads"
  - "visual discovery marketing"
inputs:
  - product_catalog
  - visual_asset_library
  - target_keywords
  - instagram_account
  - audience_goals
outputs:
  - pinterest_board_strategy
  - pin_seo_plan
  - shopping_pin_setup
  - threads_posting_plan
  - cross_posting_workflow
related_skills:
  - social-strategy
  - instagram-tiktok-organic
  - content-calendar
  - x-twitter-growth
  - marketing-paid/pinterest-ads
  - marketing-messaging/content-repurposing
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Deciding whether Pinterest or Threads (or both) fits your audience and product
- Building a Pinterest presence around visual discovery and search intent
- Selling products or driving traffic with pins and shopping/Product Pins
- Setting up a Threads presence and need a posting strategy beyond reposting Instagram
- Cross-posting from Instagram to Threads and deciding what to duplicate vs adapt
- Building community on Threads through replies, threads, and conversation

## Workflow

### Step 1: Platform Fit Decision
Decide where to invest before building anything:

- [ ] Assess Pinterest fit - strong for visual, search-driven, aspirational, or purchase-intent content (home, fashion, food, crafts, design, B2C); weak for text-heavy or enterprise B2B
- [ ] Assess Threads fit - strong for text-first conversation, brand voice, and community; inherits Instagram's audience but rewards native text
- [ ] Check audience overlap - are your buyers actually active there, or is it vanity reach?
- [ ] Set a measurable goal per platform (traffic, saves, sales, community size, replies) and agree a time-boxed experiment

**Gate:** A documented fit decision per platform with a goal and an experiment window, or an explicit choice to skip one.

### Step 2: Pinterest Account & Keyword Foundation
Treat Pinterest as a visual search engine:

- [ ] Set up a business account and claim your website to unlock analytics and rich pins
- [ ] Research keywords natively - Pinterest search suggestions and the Trends tool, not Google volumes
- [ ] Map keywords to board themes and pin titles/descriptions (search intent drives discovery, so keywords go in titles, descriptions, and board names)
- [ ] Name boards around search topics, not internal categories - "Small Apartment Ideas," not "Products"
- [ ] Optimize profile bio and board descriptions with the same keyword discipline

**Gate:** A keyword map assigned to boards, with a business account and claimed website.

### Step 3: Pin Strategy & Creation
Build a sustainable pin cadence:

- [ ] Design pins for the feed - vertical 2:3 aspect ratio, readable text overlay, high contrast (heuristic - vertical pins dominate the feed)
- [ ] Produce fresh pins per piece of content (multiple pin variations per URL) rather than a single image
- [ ] Write pin titles and descriptions as searchable copy with a clear call to action and a landing URL
- [ ] Schedule a consistent cadence - a handful of fresh pins weekly beats bursts (heuristic; consistency compounds)
- [ ] Refresh or re-pin evergreen content on a rotation rather than pinning once and forgetting

**Gate:** A repeatable pin production and scheduling workflow with SEO-complete titles and descriptions.

### Step 4: Shopping & Product Pins
Turn discovery into purchase:

- [ ] Enable Product Pins (or the shopping feed) and sync your catalog so pins show live pricing and availability
- [ ] Point each Product Pin at the exact product URL with correct, crawlable structured data on the landing page
- [ ] Create idea and collection pins that curate products around a use case or aesthetic
- [ ] Track attributed traffic and sales in Pinterest analytics, not just saves and impressions

**Gate:** Catalog synced, Product Pins live with accurate data, and conversion tracking enabled.

### Step 5: Threads Posting & Community Strategy
Build a presence native to Threads:

- [ ] Define the voice and topic lanes - Threads rewards opinion, conversation, and text-first takes over polished brand broadcast
- [ ] Post a mix of text threads, questions, and commentary on category conversations; treat it as a discussion feed, not a broadcast channel
- [ ] Join conversations by replying to relevant accounts and threads - visibility on Threads comes substantially from replies and engagement
- [ ] Experiment with post types and note what drives replies vs followers (text threads and hot takes tend to travel; heuristic observation)
- [ ] Set a posting cadence you can sustain and measure replies and follower growth, not just impressions

**Gate:** A posting plan with defined topic lanes, a cadence, and a reply-and-engage routine.

### Step 6: Cross-Posting & Repurposing
Decide what to share across platforms:

- [ ] Default Threads/Instagram cross-posting for visuals where it makes sense, but adapt captions - auto-posting identical text reads as lazy
- [ ] Repurpose top-performing content in both directions - a strong Thread gets expanded into an Instagram carousel, a strong Reel becomes a text thread
- [ ] Keep Pinterest separate - pin images and keyword copy are built for search, not social feeds, so do not auto-push social posts to boards
- [ ] Map the asset flow so one content idea feeds the right format per platform without duplicating effort

**Gate:** A documented repurposing workflow showing how each content asset moves between Pinterest, Threads, and Instagram.

## Practitioner Grounding & Decision Rules

Built from 2025-26 platform + agency intel: Shopify, Sprout Social, Pingroupie, Tailwind study, Crescitaly/Metricool analytics practice, Aibrify/Outfy Threads guides, NYT. Full research: practitioner-intelligence/syntheses/channels-longtail.md + domains/channels-longtail/pinterest-threads.md.

- **Pinterest is a search engine, not a feed** (Sprout/Shopify — FRAMEWORK, T2): 600M MAU; 90% of weekly pinners use it for purchase decisions; pinners 3x more likely to buy online weekly. Keyword-first titles/descriptions/boards; claim the website.
- **Fresh original pins at consistent cadence beat repinning** (Pingroupie/Tailwind — EMPIRICAL, T2/T3): top 1% of pins = 50% of impressions/clicks over 90 days — portfolio logic: pin at volume with fresh variations, expect most to do nothing. Old playbook (15-20 repins/day, group boards, 80/20 ratio) is dead.
- **Saves are the intent metric; clicks and conversions are the outcome** (analytics practice — HEURISTIC, T3): engagement rate = (saves+clicks)/impressions; measure outbound clicks + Pinterest Tag conversions, not impressions.
- **Threads is a conversation feed** (agency guides — HEURISTIC, T3): algorithm rewards engagement velocity (replies/reposts in first ~30 min), conversation depth, and account engagement rate; external links and repetitive promo are deprioritized. 70/20/10 conversational mix.
- **Threads organic reach is unusually high pre-monetization** (Aibrify/Outfy — OPINION, T3): ads are rolling out with intentionally low volume; the organic window won't stay open forever.
- **Cross-posting is adaptation, not duplication** (synthesis — HEURISTIC, T2/T3): identical Instagram captions on Threads read as spam; Pinterest stays keyword-native and separate from social auto-posts.

Decision rules:
1. IF the product is B2C/visual/purchase-intent (home, fashion, food, crafts, design, DTC) THEN invest in Pinterest; IF text-heavy enterprise B2B THEN skip it (Shopify/Sprout — HEURISTIC, T2).
2. IF pinning THEN: claim the website, keyword-first descriptions (first sentence = keyword + hook), 2:3 vertical pins, 3-5 hashtags max, fresh variations on a consistent cadence (Pingroupie — HEURISTIC, T3).
3. IF a pin's CTR >2x account median AND saves > median THEN promote or repin to priority boards; IF saves high but clicks low THEN fix description/CTA and verify landing-page match; IF high impressions but low closeups THEN change the hook/first 30 chars (analytics rules — HEURISTIC, T3).
4. IF measuring Pinterest THEN track saves, outbound clicks, and conversions — impressions alone prove nothing (analytics practice — HEURISTIC, T3).
5. IF posting on Threads THEN lead with conversation (opinions, questions, commentary) — ≤10% promotional; reply to everything early; use topic tags; don't lead with links (Aibrify/Outfy — HEURISTIC, T3).
6. IF cross-posting Instagram → Threads THEN adapt captions natively; keep Pinterest off the social auto-post pipeline (synthesis — HEURISTIC, T2/T3).
7. IF considering paid on either platform THEN only after ≥2 organic iterations show measurable lift (analytics rules — HEURISTIC, T3).

## Metrics

- **Pinterest:** saves (primary intent metric), outbound clicks, estimated conversions (Pinterest Tag), closeups, engagement rate = (saves+clicks)/impressions (analytics practice — HEURISTIC, T3).
- **Threads:** replies per post (primary), reach, reposts, follower growth 5-10%/mo early, profile visits from Instagram, brand mentions (Aibrify — HEURISTIC, T3).
- Guardrails: catalog sync status (products approved/taggable; 24-48h delays expected), spam-complaint-adjacent signals (auto-cross-posts suppressed).
- Re-measure: weekly 7/14/28-day snapshot; creative diagnostic top-20% vs bottom-20% pins; monthly strategic review.

## Practitioner-Sourced Failure Modes

- Treating Pinterest like Instagram — square lifestyle shots with no keyword targeting (Sprout — HEURISTIC, T2).
- Auto-cross-posting identical content to Threads — reads as spam, suppressed (agency guides — HEURISTIC, T3).
- Measuring impressions instead of saves/outbound clicks/sales (analytics practice — HEURISTIC, T3).
- Reviving dead tactics: 15-20 repins/day, group boards, 80/20 repin ratios (Tailwind-era playbook is dead — EMPIRICAL, T2).
- Broadcasting on Threads without replying — engagement is the distribution mechanism (Aibrify — HEURISTIC, T3).
- Forcing both platforms when only one fits — spread too thin to matter on either (synthesis — HEURISTIC, T2).

## Sources

1. Shopify, Pinterest Marketing Strategy Guide 2026 | shopify.com/blog/pinterest-marketing | tier 2 | 2026-08-15
2. Sprout Social, Pinterest SEO: 8 steps | sproutsocial.com/insights/pinterest-seo | tier 2 | 2026-08-15
3. Pingroupie, Pinterest SEO Guide 2026 | pingroupie.com/blog/pinterest-seo-guide-2026 | tier 3 | 2026-08-15
4. Tailwind study (top 1% of pins = 50% of impressions) via thekarareport.com | tier 3 | 2026-08-15
5. Crescitaly/Metricool, Pinterest Analytics 2026 decision rules | blog.crescitaly.com | tier 4 | 2026-08-15
6. Aibrify, Threads Marketing 2026 (algorithm factors, 70/20/10) | aibrify.com | tier 4 | 2026-08-15
7. Outfy, Threads Marketing Strategy 2026 | outfy.com | tier 4 | 2026-08-15
8. NYT, How Meta's Threads Became as Popular as X | nytimes.com | tier 2 | 2026-08-15
9. Panel: practitioner-intelligence/domains/channels-longtail/pinterest-threads.md | tier 2/3 | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Platform fit | Not assessed | Gut feel | Documented decision + goal + experiment |
| Pinterest keyword base | No research | Basic keywords | Native keywords mapped to boards |
| Pin strategy | Random pins | Scheduled | Fresh variations, SEO copy, refresh cadence |
| Shopping | Not set up | Product Pins live | Catalog synced + conversion tracked |
| Threads presence | Reposting only | Consistent posting | Native voice + reply-and-engage |
| Repurposing | Manual, ad hoc | Some cross-post | Documented asset flow |

### Common Failure Modes
- Treating Pinterest like Instagram - posting square lifestyle shots with no keyword targeting
- Auto-cross-posting identical content to Threads, which reads as spam and suppresses reach
- Setting up boards around internal product categories instead of customer search topics
- Measuring Pinterest on impressions instead of saves, outbound clicks, and sales
- Broadcasting on Threads without replying, missing the engagement mechanism that drives visibility
- Forcing both platforms when only one fits, spreading effort too thin to matter on either
