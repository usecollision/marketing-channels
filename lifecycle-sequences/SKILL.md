---
name: lifecycle-sequences
category: email
description: Design complete lifecycle email programs covering onboarding, activation, retention, and reactivation.
triggers:
  - "lifecycle email"
  - "email sequences"
  - "onboarding emails"
  - "retention emails"
  - "nurture sequence"
  - "email program"
  - "drip campaign"
inputs:
  - product_context
  - user_journey_stages
  - activation_metrics
  - churn_signals
outputs:
  - sequence_map
  - email_briefs
  - trigger_logic
  - measurement_plan
related_skills:
  - onboarding-flow
  - newsletter-framework
  - marketing-messaging/email-copy
  - marketing-optimize/signup-flow
  - marketing-optimize/funnel-analysis
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:email-platform
version: 1.0.0
---

## When to Use

Invoke when:
- Building email program from scratch
- Activation/retention metrics are below benchmarks
- Users sign up but don't activate or return
- Need to systematize ad-hoc emails into flows
- Expanding from basic welcome email to full lifecycle

## Workflow

### Step 1: Journey Mapping
Map user lifecycle stages and email opportunities:

`
Signup → Onboarding → Activation → Engagement → Retention → Expansion → Advocacy
  ↓         ↓            ↓           ↓           ↓           ↓          ↓
Welcome   Setup help   Aha moment  Usage tips   Win-back   Upsell    Referral
series    nudges       celebration deepening    re-engage  cross-sell program
`

For each stage, define:
- Trigger condition (what event starts this sequence?)
- Goal (what action should they take?)
- Exit condition (when do they leave this sequence?)
- Timing (when after trigger does each email send?)

**Gate:** All lifecycle stages mapped with triggers, goals, and exit conditions.

### Step 2: Sequence Architecture
Design each sequence:

**Welcome/Onboarding (Days 0-7):**
| Email | Timing | Subject | Goal | CTA |
|-------|--------|---------|------|-----|
| 1 | Immediate | Welcome + quick win | First value moment | Complete setup |
| 2 | Day 1 | Getting started guide | Core action | Do [key action] |
| 3 | Day 3 | Success story | Social proof + motivation | Try [feature] |
| 4 | Day 5 | Pro tip | Deeper engagement | Explore [advanced feature] |
| 5 | Day 7 | Check-in | Remove blockers | Reply with questions |

**Activation Nudges (behavioral triggers):**
| Email | Trigger | Subject | Goal |
|-------|---------|---------|------|
| 1 | Signed up, no action in 24h | Still haven't tried X? | Complete setup |
| 2 | Started but didn't finish | You're almost there | Finish onboarding |
| 3 | Used once, not returned in 3d | Quick tip to get more from... | Return visit |

**Retention/Re-engagement (Days 14-60):**
| Email | Trigger | Subject | Goal |
|-------|---------|---------|------|
| 1 | No login 7 days | What you're missing | Return |
| 2 | No login 14 days | [New feature] just launched | Return with news |
| 3 | No login 30 days | We miss you + offer | Win back |
| 4 | No login 60 days | Last chance before we... | Final attempt |

**Gate:** 3+ sequences designed with specific triggers, timing, and goals.

### Step 3: Email Archetypes
Use proven email archetypes within sequences:

1. **Quick Win** - Teach one thing they can do in 2 minutes
2. **Story** - Customer success story with relatable context
3. **Social Proof** - Metrics, testimonials, logos
4. **Feature Spotlight** - One feature + specific use case + outcome
5. **Objection Handler** - Address a common doubt or concern
6. **Milestone** - Celebrate their progress (X days, Y actions)
7. **Educational** - Teach something valuable (not just about your product)
8. **Urgency** - Trial ending, limited offer, time-sensitive
9. **Feedback** - Ask for input, survey, NPS

Mix archetypes across sequences for variety.

**Gate:** Each sequence uses 3+ different archetypes (not all the same style).

### Step 4: Copy Guidelines
Email-specific copy rules:

**Subject lines:**
- Under 40 characters for mobile
- Personalization token where natural
- Preview text extends the subject (don't repeat)
- A/B test subject lines on 20% of list before full send

**Body:**
- One idea per email (one CTA, one goal)
- Under 150 words for transactional/lifecycle
- 300-500 words for newsletters/content
- Mobile-first (short paragraphs, clear hierarchy)
- CTA button + text link (two chances to click)

**Timing:**
- Onboarding: daily for first 3-5 days, then spread out
- Nurture: 2-3x per week max
- Re-engagement: weekly, then stop after 4 attempts
- Newsletter: consistent cadence (weekly/biweekly)

**Gate:** Copy guidelines defined for subject lines, body, and timing.

### Step 5: Measurement
Track per sequence and per email:

| Metric | Benchmark | Your Target |
|--------|-----------|-------------|
| Open rate | 20-30% | |
| Click rate | 2-5% | |
| Unsubscribe | <0.5% per email | |
| Activation rate (from sequence) | Varies | |
| Revenue per email | Varies | |

Decision rules:
- Open rate <15% → Subject line problem
- Click rate <1% → Content/CTA problem
- Unsubscribe >1% → Frequency/relevance problem
- No activation lift → Wrong trigger or wrong message

**Gate:** Metrics defined with benchmarks, targets, and diagnostic rules.

## Evaluation & QA

### Common Failure Modes
- Sending the same emails to everyone (segment by behavior)
- No exit conditions (people stuck in sequences forever)
- All emails sound the same (vary archetypes and tone)
- Timing too aggressive (daily emails past day 7 = unsubscribes)
- No behavioral triggers (time-based only misses context)
- Ignoring mobile rendering (60%+ open on mobile)