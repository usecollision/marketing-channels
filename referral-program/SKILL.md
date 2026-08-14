---
name: referral-program
category: partnerships
description: Design referral programs - viral coefficient math, incentive design, in-product mechanics, double-sided rewards, and program measurement.
triggers:
  - "referral program"
  - "refer a friend"
  - "viral coefficient"
  - "referral incentives"
  - "double-sided rewards"
  - "in-product referral"
  - "viral loop"
  - "referral marketing"
inputs:
  - product_context
  - activation_definition
  - cac
  - product_flow_map
  - customer_moments
  - analytics_setup
outputs:
  - viral_model
  - incentive_design
  - in_product_spec
  - reward_fulfillment_plan
  - measurement_dashboard
  - experiment_backlog
related_skills:
  - affiliate-program
  - lifecycle-sequences
  - partnership-strategy
  - marketing-optimize/metrics-framework
  - marketing-optimize/ab-testing
  - marketing-optimize/attribution-model-selection
  - marketing-optimize/signup-flow
required_context:
  - .context/product-marketing.md
allowed_tools: []
version: 1.0.0
---

## When to Use

Invoke when:
- Deciding whether a referral program can move acquisition and how much
- Designing incentives that actually motivate sharing without breaking economics
- A referral feature exists but nobody uses it — placement, copy, or reward is wrong
- You need the viral coefficient math modeled honestly before promising growth
- Existing referral traffic is low quality or riddled with self-referral fraud

## Workflow

### Step 1: Model the Viral Math
- [ ] Model the loop: K = i × c — invites sent per active referrer (i) multiplied by conversion of invitees (c)
- [ ] Estimate i from existing behavior: how many people already share the product unprompted? That's the realistic floor (assumption — measure before designing)
- [ ] Estimate c from a landing page or waitlist test before building anything
- [ ] Be honest about decay: K above 1.0 is rare and usually decays as the audience saturates — plan for K between 0.2 and 0.4 as a healthy contribution (heuristic, not a guarantee)
- [ ] Set the target as share of new signups from referrals, plus a K tracking number

**Gate:** Viral model written with i, c, K, decay assumptions, and a realistic target share of new signups.

### Step 2: Design the Incentives
- [ ] Choose double-sided by default — single-sided rewards leave one party unmotivated; validate with your data
- [ ] Pick the reward type per product: account credit (subscription), discount (ecommerce), feature unlock (freemium), cash (marketplaces)
- [ ] Size the reward against CAC: total reward cost for a referred customer must stay well below paid CAC (assumption — compute it, don't guess)
- [ ] Make the reward feel meaningful: a reward below the threshold of caring generates zero shares
- [ ] Decide reward timing: on signup vs on activation — paying on activation filters junk referrals

**Gate:** Double-sided incentive chosen, reward economics computed against CAC, timing rule decided.

### Step 3: Design In-Product Mechanics
- [ ] Pick placement from real customer moments: right after activation success, post-purchase confirmation, when a teammate is invited to collaborate, after a support win
- [ ] Rule: ask for a referral at the moment of delight, not during onboarding friction (assumption — test against your moments)
- [ ] Remove friction from sharing: pre-filled message with the referrer's voice, one-tap share buttons, a personal link always available in settings
- [ ] Show the referrer status: who joined, what reward was earned, what's pending — visibility sustains participation
- [ ] Wire the invitee experience: the landing page must answer what the product is, why the friend sent it, and what the invitee gets

**Gate:** Placement, share flow, status surface, and invitee landing page specified and wired.

### Step 4: Build Fulfillment and Edge Cases
- [ ] Automate reward delivery — manual fulfillment caps the program's scale from day one
- [ ] Define redemption rules: expiry, stacking with other discounts, minimum spend if any
- [ ] Handle the edge cases explicitly: self-referral blocked, existing customers excluded from invitee rewards, same-household rules, refunds reversing rewards
- [ ] Write the in-product error and pending states — a stuck reward is worse than no reward
- [ ] Set a support path for reward disputes with a clear policy

**Gate:** Fulfillment automated, edge cases enumerated with rules, support policy written.

### Step 5: Add Quality Controls
- [ ] Enforce one reward per unique customer — device and payment fingerprinting where economics justify it
- [ ] Watch for the fraud patterns: fake accounts at scale, coupon resale, invitee churn right after reward
- [ ] Define what counts as a qualified referral: activated, paying, retained for N days — and pay only on qualified
- [ ] Cap abuse levers: per-referrer limits, slower payout for large or suspicious amounts
- [ ] Monitor invitee quality, not just volume — referral customers with terrible retention are a hidden cost

**Gate:** Qualification definition set, abuse limits configured, quality monitoring in the dashboard.

### Step 6: Measure and Experiment
- [ ] Instrument the full funnel: impressions → shares → clicks → signups → activation → revenue per stage
- [ ] Track the program metrics monthly: K, share of new signups, reward cost vs CAC, referred customer LTV
- [ ] Build the experiment backlog: incentive size, reward type, placement, copy, share-channel mix — test one variable at a time (see marketing-optimize/ab-testing)
- [ ] Re-run the viral model quarterly with real i and c — replace assumptions with measurements
- [ ] Cut what doesn't work: kill placements and rewards that produce impressions but no shares

**Gate:** Funnel instrumented end-to-end, dashboard live, experiment backlog prioritized, model refresh scheduled.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Viral math | K assumed from a blog post | i and c estimated | Model with decay + measured quarterly refresh |
| Incentives | Copied from a competitor | Double-sided chosen | Reward economics computed against CAC, paid on activation |
| Mechanics | Buried in settings | Placed at a customer moment | Friction-free share flow + referrer status surface |
| Fulfillment | Manual | Automated | Edge cases enumerated + automated + support policy |
| Measurement | Signups counted | Funnel tracked | Qualified referrals + quality + experiment loop running |

### Common Failure Modes
- Asking for referrals at the wrong moment — onboarding friction kills the ask
- Single-sided rewards that motivate exactly one party
- Presenting K as a growth guarantee instead of a modeled assumption with decay
- Counting signups while activation and retention of referred users go unmeasured
- Rewards too small to care about — the program ships and nobody shares
- Manual reward fulfillment that collapses at the first volume spike
- Ignoring self-referral and abuse until payouts balloon
