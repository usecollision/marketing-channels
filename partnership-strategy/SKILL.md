---
name: partnership-strategy
category: partnerships
description: Pick and run the right partner types - integration, channel, agency, and community - with scoring, tiering, co-marketing planning, and GTM economics.
triggers:
  - "partnership strategy"
  - "channel partners"
  - "integration partners"
  - "partner program"
  - "partner tiering"
  - "partner scoring"
  - "co-marketing planning"
  - "agency partnerships"
inputs:
  - product_context
  - icp
  - gtm_goals
  - partner_landscape
  - team_capacity
  - unit_economics
outputs:
  - partner_type_mix
  - partner_scorecard
  - tiering_model
  - co_marketing_plan
  - gtm_economics_model
  - partnership_measurement_plan
related_skills:
  - co-marketing
  - affiliate-program
  - ambassador-program
  - creator-outreach
  - product-launch-playbook
  - marketing-intelligence/gtm-plan
  - marketing-intelligence/competitor-audit
  - marketing-messaging/sales-deck
  - marketing-optimize/metrics-framework
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Deciding whether partnerships deserve a seat in the GTM and which partner types earn it
- Weighing integration vs channel vs agency vs community partners for a specific goal
- The partner pipeline is a list of names, not a scored and tiered portfolio
- Co-marketing requests arrive ad hoc and get decided by whoever shouts loudest
- You need to model whether a partner motion pays for itself in CAC, margin, and LTV

## Workflow

### Step 1: Define the Job Partners Do
- [ ] Name the primary goal: pipeline, signups, distribution, credibility, retention — pick one primary
- [ ] Write a one-line job statement: partners exist to do X for Y audience that direct GTM cannot
- [ ] Commit capacity honestly: partner management is people-heavy; as a rough heuristic one full-time partner manager can actively support roughly 20-30 productive partners (heuristic — validate against your own data)
- [ ] Define success metrics per goal before signing anyone (sourced pipeline, influenced revenue, activation rate)
- [ ] Agree who owns partnerships internally — scattered ownership kills partner motions

**Gate:** Job statement written, primary goal chosen, capacity and ownership committed, success metrics defined.

### Step 2: Pick Partner Types
- [ ] Integration partners — product-level tie-ins (API, marketplace listing, native flows). Best for discovery inside another product's workflow, churn reduction, and credibility with technical buyers. Cost - engineering time and ongoing maintenance
- [ ] Channel partners — resellers, agencies, consultancies that sell or implement for you. Best for markets your direct motion can't reach and services-led buying. Cost - margin, enablement, channel conflict
- [ ] Agency partners — firms that build on or deliver your product; a hybrid of channel and community
- [ ] Community/ecosystem partners — platforms, communities, and creators that distribute without transacting
- [ ] Match types to ICP buying behavior: where do buyers already place trust?
- [ ] Cap the number of active types at what the team can genuinely support (assumption — deliberate focus beats breadth)

**Gate:** One to two primary partner types chosen with rationale tied to ICP behavior and capacity.

### Step 3: Build the Partner Scorecard
- [ ] Score dimensions (1-5 each): audience/ICP overlap, reach or deal volume, product complementarity, trust and influence in the category, activation effort, expected time to first result
- [ ] Weight dimensions by the primary goal — overlap and influence dominate awareness plays; deal volume dominates channel plays
- [ ] Treat scores as hypotheses: record the score and the evidence behind it, then validate against real results
- [ ] Score at least 20 candidates before tiering so tiers are relative, not arbitrary
- [ ] Set kill criteria up front — partners below the overlap threshold go to a nurture list, not the active portfolio

**Gate:** Weighted scorecard applied to 20+ candidates with evidence noted and kill criteria documented.

### Step 4: Tier and Design Benefits
- [ ] Tier by contribution, not brand: strategic/core (few, deeply managed), growth (many, semi-automated), long-tail (self-serve)
- [ ] Design a benefits ladder per tier: co-marketing budget, dedicated manager, early access, revenue share, MDF
- [ ] Define commitments both ways — a partner agreement that says what each side delivers per tier, in writing
- [ ] Keep tier movement rules explicit: promotion criteria and demotion criteria published, not vibes
- [ ] Review the tier split quarterly against contribution data

**Gate:** Three-tier model with benefits ladder, mutual commitments, and promotion/demotion rules documented.

### Step 5: Plan Co-Marketing and Model GTM Economics
- [ ] Map joint campaigns onto the calendar per tier (see co-marketing for campaign mechanics)
- [ ] Model economics per partner type: cost per partner (management time, rev share or margin, co-marketing budget) vs expected contribution (pipeline, revenue, retention)
- [ ] Set a payback expectation: a partner motion should show leading indicators (first sourced deals, first joint leads) within about two quarters (assumption — validate with your data)
- [ ] Run the cannibalization check: define rules of engagement between channel partners and direct sales before the first conflict
- [ ] Stress-test the model: what happens to margin if the top partner goes exclusive with a competitor?

**Gate:** Economics model built for the primary type and rules of engagement documented.

### Step 6: Govern and Measure
- [ ] Partner health dashboard: sourced pipeline, influenced revenue, co-marketing performance, partner activation rate
- [ ] QBR rhythm for strategic partners; automated reporting for the long tail
- [ ] Annual portfolio review: promote, demote, or kill tiers based on trailing data
- [ ] Feed results back into the scorecard — weights should change as data replaces guesses
- [ ] Document what worked into a partner playbook so new partner managers don't start from zero

**Gate:** Dashboard live, QBR calendar set, annual review scheduled, scorecard updated with validated weights.

## Practitioner Grounding & Decision Rules

Built from Geno Prussakov (affiliate), Misha Talavera (Viral Loops), Joe Gagliese (influencer), Sean Ellis (referral). Full research: practitioner-intelligence/syntheses/partnerships.md.

- **Terms/creatives/tracking before recruitment** (Prussakov — FRAMEWORK, T1): the #1 affiliate setup rule — launch with documentation, not promises.
- **Referral K < 0.15 = assist channel** (Talavera — HEURISTIC, T2): below that coefficient, don't staff for virality.
- **Fix product before referral** (Ellis — HEURISTIC, T1): NPS < ~30 or weak retention means referral amplifies churn.
- **Influencer requires measurement plan before spend** (Gagliese — FRAMEWORK, T2): lift or paid-benchmark comparison, not vanity metrics.

Decision rules:
1. IF launching an affiliate program THEN write terms, creatives, and tracking first; recruit 10-20 quality affiliates before scaling (Prussakov — FRAMEWORK, T1).
2. IF referral coefficient K < 0.15 THEN treat referral as an assist channel — don't staff or budget for virality (Talavera — HEURISTIC, T2).
3. IF NPS < ~30 or retention is weak THEN fix product/retention before launching referral (Ellis — HEURISTIC, T1).
4. IF spending on influencers THEN require a measurement plan (lift test or paid-benchmark comparison) before budget approval (Gagliese — FRAMEWORK, T2).
5. IF a partner type has no measurable contribution to a business metric THEN drop it — partnership without attribution is sponsorship (synthesis — FRAMEWORK, T2).

## Metrics

- **Affiliate**: EPC, share of program revenue, top-20 affiliate concentration (Prussakov — FRAMEWORK, T1).
- **Referral**: K coefficient, cycle time, conversion per stage (Talavera — HEURISTIC, T2).
- **Influencer**: lift vs holdout or paid-benchmark, not impressions (Gagliese — FRAMEWORK, T2).

## Sources

1. Geno Prussakov, *Affiliate Program Management* / AM Navigator | amnavigator.com | tier 1 | 2026-08-15
2. Misha Talavera, referral program playbooks (Viral Loops) | viral-loops.com | tier 2 | 2026-08-15
3. Sean Ellis, referral loops | growthhackers.com | tier 1 | 2026-08-15
4. Joe Gagliese, influencer measurement (Viral Nation) | viralnation.com | tier 2 | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Type selection | Partner types chosen by enthusiasm | One type chosen with rationale | Type tied to ICP behavior and capacity |
| Scoring | List of names | Scored candidates | Weighted scorecard, evidence noted, validated later |
| Tiering | Everyone treated the same | Tier labels exist | Benefits ladder + mutual commitments + movement rules |
| Economics | No cost model | Cost model built | Margin and cannibalization stress-tested with payback targets |
| Governance | Metrics reported ad hoc | Dashboard live | QBR + annual review + scorecard feedback loop |

### Common Failure Modes
- Signing partners for the logo, not the pipeline
- Running all four partner types as one undifferentiated program
- Scorecard theater — scores that are never validated against actual results
- Ignoring margin math — rev share quietly erodes unit economics
- Portfolio growth without management capacity growth
- No rules of engagement — channel conflict poisons the direct sales team
- Strategic partners that receive effort but produce nothing for three quarters
