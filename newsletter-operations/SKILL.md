---
name: newsletter-operations
category: email
description: Run a newsletter as a channel - format design, cadence discipline, growth loops, engagement mechanics, monetization paths, and the metrics that matter.
triggers:
  - "newsletter"
  - "newsletter strategy"
  - "newsletter growth"
  - "newsletter monetization"
  - "newsletter metrics"
  - "email newsletter"
inputs:
  - audience_research
  - content_pipeline
  - subscriber_list
  - positioning
outputs:
  - newsletter_format
  - cadence_plan
  - growth_plan
  - engagement_dashboard
  - monetization_plan
related_skills:
  - lifecycle-sequences
  - email-deliverability
  - content-calendar
  - community-strategy
  - marketing-messaging/email-copy
  - marketing-optimize/analytics-setup
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Starting a newsletter from zero
- Subscriber growth is flat
- Open/click rates are declining
- Exploring monetization (sponsors, paid tier, product)
- Deciding cadence, format, or platform changes

## Workflow

### Step 1: Format & Promise Design
Define what the newsletter IS before anything else:

- **One-sentence promise** - what value the reader gets every issue (example patterns - "the 5 best X every Friday", "one deep teardown per week", "the tactics roundup for Y")
- **Format archetype** - curated links, original essay, story-driven, tactical teardown, data roundup, or hybrid; pick one primary plus one secondary
- **Issue structure** - fixed sections readers recognize (opener, core, links, closer)
- **Length** - short enough to finish in one sitting (common heuristic - under 5 minutes of reading; adjust to your audience)
- **Voice** - a consistent persona across issues (see marketing-messaging/brand-voice)

**Gate:** Written format brief with promise, archetype, section template, and length target.

### Step 2: Cadence & Production Pipeline
- **Cadence** - weekly is the default heuristic for most B2B audiences; daily only with a dedicated operator; monthly rarely builds habit
- **Send day/time** - test once, then hold constant; shifting constantly destroys habit formation
- **Production pipeline** - capture system → draft → edit → send checklist (links verified, unsubscribe and footer present, deliverability checks per email-deliverability)
- **Editorial backlog** - keep several issues of material staged so quality never depends on weekly inspiration
- **Platform selection** - email-first tools (Beehiiv, Substack, ConvertKit, ESP-native) chosen for automation, referral tooling, and monetization needs

**Gate:** Production calendar with owner, checklist, and a staged backlog.

### Step 3: Growth Strategy
- **Owned channels** - homepage signup module, post-purchase, in-product, blog inline forms
- **Social distribution** - repurpose issue content as posts; lead with a strong pull-quote (see x-twitter-growth, linkedin-content)
- **Cross-promotions and swaps** - partner newsletters with adjacent, non-competing audiences; recommend-for-recommend placements
- **Referral mechanics** - built-in referral rewards with milestone tracking (heuristic - expect a small fraction of subscribers to participate; don't gate core content behind referrals early)
- **Lead magnets** - upgrade the signup offer with a useful artifact (checklist, database, template)
- **Paid acceleration** - sponsor other newsletters or run list-building ads only after organic conversion is proven

**Gate:** Growth plan with 3+ active loops and per-channel targets.

### Step 4: Engagement Tactics
- **Subject lines** - specific over clever; test curiosity gaps (see marketing-messaging/email-copy)
- **Reply bait** - end issues with a question and reply to every response in the first hours
- **Reader-led content** - solicit questions, run polls, feature reader wins
- **Segmentation** - split engaged vs dormant; prune chronic non-openers on a quarterly heuristic to protect deliverability
- **Community loop** - route engaged readers into the community and bring community moments back into the newsletter

**Gate:** Engagement system with reply-bait, segmentation rules, and prune policy.

### Step 5: Monetization Options
Choose based on subscriber base and niche:

- **Sponsorships** - the default for curated/utility newsletters; price on CPM heuristics, sell per-issue placements, disclose clearly
- **Classifieds/job board** - works for niche professional audiences
- **Paid subscription tier** - fits deep original analysis; expect only a fraction of free subscribers to convert (heuristic - single-digit percentages in most cases; verify for your niche)
- **Product cross-sell** - the highest-leverage path when the newsletter feeds a product or consulting business; measure newsletter-influenced revenue
- **Match the model to the format** - sponsors need scale plus engagement; paid needs depth plus uniqueness; product needs ICP fit

**Gate:** Monetization path chosen with revenue model, pricing, and a no-go decision point (subscriber threshold or engagement floor).

### Step 6: Metrics That Matter
- **North star** - active subscribers (opened in the last 30-90 days) or weekly replies, not raw list size
- **Growth funnel** - signup → confirmed → active → referring
- **Engagement** - open rate, click-through, reply rate, per-issue unsubscribes
- **Delivery health** - spam complaints, bounce rate, inbox placement (see email-deliverability)
- **Monetization** - revenue per issue, CPM, sponsor renewal rate
- **Benchmarks** - treat external open-rate benchmarks as rough reference only; compare against your own trailing average

**Gate:** Dashboard with 5-8 core metrics, weekly review, and alert thresholds.

## Evaluation & QA

### Newsletter Health Rubric
| Criteria | Weak | OK | Strong |
|----------|------|----|--------|
| Promise clarity | Generic "news and insights" | Specific topic | Specific promise + named audience |
| Cadence | Irregular | Consistent weekly | Consistent + held day/time |
| Engagement | Rare replies | Replies occasionally | Weekly reply threads |
| Growth | Flat list | Steady owned-channel adds | Multiple compounding loops |
| Monetization | None | One stream | Diversified with newsletter-attributed revenue |

### Common Failure Modes
- No defined promise - the newsletter competes with everything and wins nothing
- Chasing raw subscriber count with low-intent giveaways (deliverability decay + fake engagement)
- Cadence chaos - gaps train readers to forget you
- Monetizing before the audience trusts the format
- Optimizing open rates with clickbait that erodes trust
- No prune policy - dormant subscribers drag sender reputation
