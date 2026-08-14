---
name: community-strategy
category: community
description: Build communities on Discord, Telegram, or Slack - onboarding, rituals, moderation, and flywheel metrics.
triggers:
  - "community strategy"
  - "Discord server"
  - "Telegram group"
  - "Slack community"
  - "community building"
  - "community onboarding"
  - "community moderation"
  - "community metrics"
inputs:
  - product_context
  - icp
  - community_purpose
  - platform_constraints
  - team_capacity
outputs:
  - platform_decision
  - channel_architecture
  - onboarding_flow
  - rituals_calendar
  - moderation_playbook
  - flywheel_metric_dashboard
related_skills:
  - social-strategy
  - reddit-engagement
  - lifecycle-sequences
  - content-calendar
  - marketing-messaging/brand-voice
  - marketing-intelligence/customer-research
  - marketing-intelligence/social-listening
  - marketing-optimize/metrics-framework
required_context:
  - .context/product-marketing.md
allowed_tools: []
version: 1.0.0
---

## When to Use

Invoke when:
- Deciding whether a community is the right investment and which platform fits
- Launching a Discord, Telegram, or Slack community from zero
- Existing community is a ghost town — members join and never return
- Moderation is reactive, ad-hoc, and burning out the team
- Need to prove community value with metrics beyond member count

## Workflow

### Step 1: Purpose & Platform Selection
- [ ] Define the community's job precisely: support deflection, retention, acquisition, feedback, or advocacy — one primary job
- [ ] State who it's for and what members get that they can't get elsewhere
- [ ] Platform fit: Discord (real-time, younger/dev/gamer cultures), Slack (B2B professional, invite-only feel, but cost and noise), Telegram (global, mobile, broadcast-friendly)
- [ ] Match platform culture to ICP habits — meet members where they already are
- [ ] Write the "why this exists" statement; if it doesn't survive scrutiny, don't build it

**Gate:** Purpose statement written, primary job chosen, platform decision made with rationale.

### Step 2: Structure & Onboarding Design
- [ ] Channel architecture: start minimal — every channel needs a clear purpose and expected behavior (fewer channels = more activity; heuristic)
- [ ] Onboarding flow: welcome ritual, intro template (who you are, what you're working on), rules acceptance, first action within minutes
- [ ] Design the first-week experience: what should a new member have done by day 7 (intro posted, one reply, one resource used)?
- [ ] Member journey map: newbie → regular → power member → advocate, with a visible path between stages
- [ ] Appoint greeters: real humans (or well-tuned bot flows) who reply to every intro within hours

**Gate:** Onboarding flow live with intro template, rules gate, and a defined first-week target; journey map documented.

### Step 3: Rituals & Programming
- [ ] Recurring rituals: weekly threads (wins, asks, help), AMAs, office hours, demos, challenges
- [ ] Recognition systems: roles/badges, member spotlights, milestone celebrations (first contribution, 100th post)
- [ ] Founder presence ritual: a fixed, honest founder touchpoint (weekly AMA or voice note) — consistency over frequency
- [ ] Content rituals: member-generated prompts (build in public, share your stack) that generate ongoing material
- [ ] Calendar the rituals; rituals that aren't scheduled don't happen

**Gate:** Rituals calendar live for 4+ weeks ahead, each with an owner, cadence, and recognition element.

### Step 4: Moderation & Governance
- [ ] Write rules: short, explicit, behavior-based (what's banned, what's encouraged), pinned in every surface
- [ ] Moderation ladder: warn → mute → remove → ban, with documented escalation triggers — no ad-hoc punishment
- [ ] Recruit mods from active members; train them; watch for burnout and rotate before it happens
- [ ] Crisis protocol: harassment, spam waves, leaks, platform outages — pre-agreed response steps
- [ ] Automate the repetitive: spam filters, onboarding bots, slow-mode during incidents

**Gate:** Moderation playbook written and agreed; escalation ladder and crisis protocol tested with mods.

### Step 5: Flywheel Metrics
- [ ] Define the loop: new member → activation event (first contribution) → recurring participation → invites/advocacy
- [ ] Core metrics: activation rate, weekly active participation, cohort retention (do week-1 members return week 5?), invite rate, member-generated content volume
- [ ] Business tie-ins: support deflection, referrals, NPS lift, churn reduction — validate with your data (assumption until proven)
- [ ] Instrument before launch: capture join → activation → participation timestamps from day one
- [ ] Report monthly: size is vanity, activation and retention are the flywheel

**Gate:** Metric dashboard live from launch; monthly report reads the flywheel, not the member count.

### Step 6: Growth & Lifecycle Ops
- [ ] Launch plan: seed with founding members (a core of engaged early members — a committed dozen beats a passive thousand; heuristic), personal invites from founders
- [ ] Distribution: promote via content channels, lifecycle emails, and post-purchase flows (see lifecycle-sequences)
- [ ] Lifecycle management: re-engage dormant members, prune dead channels, evolve rituals as the community matures
- [ ] Health pulse: sample member sentiment regularly — one unhappy power member can set the tone
- [ ] Annual reset: re-test the purpose statement against reality; kill or pivot the community if the job changed

**Gate:** Launch executed with seeded founding members; quarterly health review scheduled with re-engagement and pruning actions.

## Practitioner Grounding & Decision Rules

Practitioners: Rich Millington (FeverBee — evidence-based community ROI, T2), David Spinks (CMX — community flywheels, T3 this session), Carrie Melissa Jones (lifecycle + moderation science, T3 this session).

- IF a community exists without a stated business purpose THEN fix purpose before adding tools/features — communities fail from unclear purpose and under-investment, not tools (Millington/Spinks/Jones, FRAMEWORK, T2).
- IF you're reporting activity (posts, DAU) as success THEN switch to value behaviors + business outcomes — activity-boosting tactics raise costs more than value (Millington, FRAMEWORK, T1 as essay).
- IF goal is retention THEN design for the 6 value behaviors: ask questions about the product; read product/mission info; introduce yourself; private discussions; reveal personal details; answer questions for credibility (Millington, FRAMEWORK, T1).
- IF members' questions go unanswered THEN staff an answer SLA before growing membership — fast brand answers drive perceived brand value (Millington, HEURISTIC, T2).
- IF justifying budget THEN tie community to support deflection / retention lift of members vs non-members, not "engagement" (Millington, FRAMEWORK, T2).
- IF members aren't forming connections THEN add rituals for introductions/private spaces — group identity is a loyalty driver (Millington, FRAMEWORK, T1).
- IF a discussion can't be mapped to a value behavior or business outcome THEN treat it as cost, not community health (Millington, HEURISTIC, T2).

## Metrics

- Primary: value behaviors per active member/month; retention lift of community members vs non-members; support deflection rate.
- Guardrails: question-answer SLA (e.g., <24h), % members with private connections, moderation incident rate.
- Timebox: quarterly value review; 6 months before judging ROI.
- When to re-measure: after purpose redefinition, after moderation staffing changes, or when activity grows but value behaviors stay flat for 2 quarters (kill the activity theater).

## Sources

1. Millington, "Generating A Positive ROI For Your Community" | https://www.feverbee.com/positive-roi/ | T1 | 2026-08-15
2. Spinks, CMX archives (flywheel canon) | https://cmxhub.com | T3 | 2026-08-15
3. Jones, Building Brand Communities (lifecycle/moderation) | T3 (not fetched this session) | 2026-08-15
4. Synthesis: syntheses/social.md (§Community) | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Purpose | Built "because everyone has one" | Job defined | Purpose + platform + ICP fit rationale |
| Onboarding | Join and wander | Welcome message | Ritual + first action + day-7 target |
| Rituals | Nothing scheduled | Some events | Calendar with owners + recognition |
| Moderation | Reactive chaos | Some rules | Ladder + crisis protocol + mod care |
| Metrics | Member count | Activity tracked | Flywheel loop instrumented from day one |

### Common Failure Modes
- Building the platform before defining the purpose — structure without strategy
- Channel sprawl: 30 channels and 3 active ones scares new members away
- Founder-led everything: when the founder burns out, the community dies
- Measuring size instead of activation and retention
- No moderation plan until the first crisis forces one
- Using the community as a promo channel — members leave communities that sell at them
