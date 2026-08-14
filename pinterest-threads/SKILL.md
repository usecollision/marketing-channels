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
