---
name: affiliate-program
category: partnerships
description: Design an affiliate program - commission structures, network vs in-house, recruitment, tracking setup, fraud prevention, and affiliate enablement.
triggers:
  - "affiliate program"
  - "affiliate marketing"
  - "commission structure"
  - "affiliate network"
  - "affiliate tracking"
  - "affiliate fraud"
  - "affiliate recruitment"
  - "affiliate management"
inputs:
  - product_context
  - unit_economics
  - cac_target
  - existing_advocates
  - platform_options
  - team_capacity
outputs:
  - commission_model
  - platform_decision
  - tracking_spec
  - recruitment_plan
  - fraud_policy
  - enablement_pack
related_skills:
  - partnership-strategy
  - referral-program
  - influencer-marketing
  - creator-outreach
  - marketing-optimize/metrics-framework
  - marketing-optimize/utm-governance
  - marketing-optimize/crm-pipeline-attribution
required_context:
  - .context/product-marketing.md
allowed_tools: []
version: 1.0.0
---

## When to Use

Invoke when:
- Evaluating whether an affiliate program is the right acquisition channel
- Deciding between an affiliate network and running the program in-house
- Structuring commissions without wrecking unit economics
- Existing affiliates are dormant, unmanaged, or producing junk traffic
- Affiliate-sourced sales need trustworthy tracking and fraud protection
- You want to recruit affiliates systematically instead of waiting for applications

## Workflow

### Step 1: Model the Economics and Set the Commission
- [ ] Establish the ceiling: maximum acceptable CAC from the blended acquisition model — affiliate cost must fit inside it
- [ ] Model commission as a share of customer value: lifetime value (LTV), not order value, decides what you can pay for subscription products (assumption — validate with your data)
- [ ] Reference category norms only as a starting point — commission rates vary wildly by niche, and norms are not targets (heuristic)
- [ ] Set the base rate, then add performance tiers: higher volume or better-quality affiliates earn more
- [ ] Pick the cookie window deliberately — longer windows increase affiliate appetite and cannibalization risk; 30 days is a common default (heuristic — test against your sales cycle)

**Gate:** Commission model written with CAC ceiling, base rate, tiers, and cookie window — each justified by economics.

### Step 2: Choose Network vs In-House
- [ ] Network: fastest to launch, built-in affiliate marketplace and recruitment, handled payouts and fraud tooling — at a platform fee plus network override on top of commissions
- [ ] In-house: full control, no network fee, direct relationships — but you build tracking, payouts, and fraud detection yourself
- [ ] Decision drivers: budget, speed to first revenue, whether you need the network's existing affiliate pool, and team capacity to manage affiliates
- [ ] Hybrid path is common: start on a network for speed, evaluate in-house once volume justifies the build (heuristic)
- [ ] Get real fee quotes before deciding — network pricing varies with volume tiers

**Gate:** Platform decision made with quoted costs and a documented tradeoff rationale.

### Step 3: Set Up Tracking and Attribution
- [ ] Define the tracking chain: affiliate link or code → click → session → conversion, with the affiliate ID captured on signup
- [ ] Decide attribution rules: last-click vs first-click vs split — write the rule down and make it consistent with paid channels (see marketing-optimize/crm-pipeline-attribution)
- [ ] Integrate with billing early: commission events must map to actual paid revenue, not free trials
- [ ] Set refund and chargeback policy: commissions clawed back on refunds — automate it, don't chase manually
- [ ] Test the full path end-to-end before recruiting a single affiliate

**Gate:** Tracking verified end-to-end on a test transaction; attribution and clawback rules documented.

### Step 4: Recruit Affiliates
- [ ] Profile the ideal affiliate: who already has your ICP's attention — creators, niche newsletters, communities, comparison sites, happy customers
- [ ] Mine existing advocates first: customers who refer already, power users, creators who mention the product organically
- [ ] Source lists: competitor affiliate programs (who promotes them), platform marketplaces, industry events
- [ ] Set application criteria and a quality bar — volume of affiliates is vanity if traffic quality is low
- [ ] Outreach with a personal pitch naming why their audience fits (see creator-outreach for sequence mechanics)

**Gate:** Ideal affiliate profile written, first 20-30 outreach targets sourced and contacted.

### Step 5: Prevent Fraud
- [ ] Red flags to monitor: brand bidding on your own name, cookie stuffing, self-referral, incentive abuse, bot traffic spikes, duplicate accounts
- [ ] Write the program rules with explicit prohibited activities and penalties — publish them on the signup page
- [ ] Configure platform fraud tools: duplicate IP and device detection, geo checks, conversion pattern alerts
- [ ] Review payouts before they go out — a monthly manual scan of top earners catches most schemes (assumption)
- [ ] Slow-roll new affiliates: watch the first month of activity before raising commission tiers

**Gate:** Fraud policy published, platform rules configured, payout review step in the monthly cadence.

### Step 6: Enable and Optimize Affiliates
- [ ] Build the enablement pack: approved copy, visuals, product one-pager, demo links, promo codes, landing pages
- [ ] Give affiliates a dashboard they can actually read — earnings, clicks, conversions, and what's performing
- [ ] Run a monthly newsletter: new assets, top performer tips, product updates worth promoting
- [ ] Review affiliate cohorts monthly: top earners to nurture, mid-tier to coach, dormant to re-engage or prune
- [ ] Report the channel honestly: revenue, margin after commissions, and customer quality (retention of affiliate-sourced customers vs other channels)

**Gate:** Enablement pack live, affiliate dashboard shipped, monthly review cadence running with cohort actions.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Commission | Category default copied | Tied to CAC ceiling | LTV-based with tiers and tested cookie window |
| Platform | Chosen by hype | Tradeoffs documented | Quoted costs + hybrid migration path |
| Tracking | Trusts the platform | End-to-end tested | Attribution and clawback rules written and automated |
| Recruitment | Waits for applications | Sourced a target list | Advocates mined + outbound sequence running |
| Fraud | None until the first incident | Rules published | Platform tooling + payout review + slow-roll policy |

### Common Failure Modes
- Commission set by copying a competitor without CAC math — the program leaks margin
- Launching before the tracking path is tested — affiliates promote and conversions vanish
- Paying on trials or unqualified events — commission outflows without revenue
- No fraud policy until the first expensive scheme is discovered
- Recruiting volume over quality and filling the program with junk traffic
- Affiliates left without assets, dashboards, or communication — a dormant roster within a quarter
- Judging the channel on raw revenue while customer quality quietly declines
