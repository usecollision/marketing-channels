---
name: events-webinars
category: events
description: Plan events and webinars - format selection, topic and speaker design, promotion, attendance conversion, and follow-up sequences.
triggers:
  - "webinar"
  - "virtual event"
  - "in-person event"
  - "workshop"
  - "event promotion"
  - "no-show rate"
  - "meetup"
inputs:
  - event_goal
  - target_audience
  - speaker_pool
  - budget
  - team_capacity
outputs:
  - event_plan
  - format_decision
  - promotion_plan
  - registration_page_spec
  - followup_sequence
  - post_event_report
related_skills:
  - product-launch-playbook
  - content-calendar
  - lifecycle-sequences
  - marketing-intelligence/customer-research
  - marketing-intelligence/survey-design
  - marketing-optimize/funnel-analysis
required_context:
  - .context/product-marketing.md
allowed_tools: []
version: 1.0.0
---

## When to Use

Invoke when:
- Choosing between webinar, workshop, roundtable, or in-person event for a goal
- Registration numbers are fine but attendance keeps disappointing
- Planning a launch-adjacent or demand-gen event (see product-launch-playbook)
- Building a repeatable event engine instead of one-off webinars
- Deciding whether virtual or in-person fits the audience and budget

## Workflow

### Step 1: Choose the Format and Topic
- [ ] Format menu: webinar (reach, demand gen), workshop (deep value, leads), roundtable or panel (credibility, relationships), AMA (community), in-person meetup (local density), hybrid (reach + local depth)
- [ ] Match format to goal: demand gen wants webinars; trust-building wants workshops and roundtables
- [ ] Topic scoring: audience pain x your expertise x search or demand signal x differentiation from what already exists
- [ ] Validate with a quick check: would your ICP forward the invite to a colleague? If not, the topic is weak
- [ ] Decide virtual vs in-person: audience geography, budget, production capacity, and relationship depth needed (heuristic)

**Gate:** Format and topic chosen with a written goal-format-topic rationale.

### Step 2: Design Speakers and the Run of Show
- [ ] Speaker mix: internal expert + customer (strongest proof) + optional external name for draw
- [ ] Brief every speaker: audience, goal, key messages, what not to pitch
- [ ] Run of show: 45-60 minutes total for webinars (heuristic) — 5 min intro, 25-35 min content, 15 min Q&A; workshops can run longer with hands-on blocks
- [ ] Build interaction beats: polls, live questions, takeaway moments — the first 5 minutes decide retention
- [ ] Rehearse once with all speakers; record it as the backup

**Gate:** Run of show timed to the minute, speakers briefed, one rehearsal completed.

### Step 3: Build the Registration Funnel
- [ ] Landing page: one benefit headline, what you will learn, speaker credibility, date and time with timezone, low-friction form
- [ ] Confirmation email: calendar invite file, reminder of value, one-click cancel
- [ ] Reminder schedule: 7 days (value reminder), 1 day, 1 hour before (heuristics)
- [ ] Set up tracking: registration source, attendance, engagement, follow-up clicks
- [ ] No-show is normal — commonly cited attendance ranges are roughly 30-50% of registrants for webinars; treat published benchmarks as rough priors and calibrate with your own data (do not quote as fact)

**Gate:** Funnel live end to end with tracking on every step.

### Step 4: Promote
- [ ] Email: 2-3 sends to the house list segmented by relevance; partners and speakers send to their audiences too
- [ ] Social: speaker-led posts outperform brand posts — give speakers pre-written copy and visuals
- [ ] Communities: post where the audience lives, only where you are an active member
- [ ] Pacing: open registration 2-3 weeks out, push hardest in the final 72 hours (heuristic)
- [ ] Budget decision: paid promotion only when organic channels are maxed or the goal is net-new audience

**Gate:** Promotion plan with channel, owner, and timing; speakers confirmed to promote.

### Step 5: Maximize Live Attendance and Engagement
- [ ] Day-before and hour-before reminders are the highest-leverage sends — do not skip
- [ ] Offer the replay as a reason to register, not as a substitute for attending (live Q&A is the differentiator)
- [ ] During: start on time, state the one takeaway up front, moderate questions, log unanswered questions for follow-up
- [ ] Have a producer role — someone other than the speaker runs tech, chat, and timing
- [ ] If attendance is low, run the session anyway with full energy — recordings become on-demand assets

**Gate:** Reminders sent on schedule, session run to the run of show, all questions captured.

### Step 6: Follow Up
- [ ] Within 24 hours: thank-you email with replay link and the slide deck (heuristic)
- [ ] Non-attendee sequence: 2-3 emails over a week offering the replay and the key takeaway — many non-attendees still consume the recording
- [ ] Segment by engagement: attended + asked questions = warmest; route to sales with context
- [ ] Survey: 3-5 questions on value and future topics (see survey-design for method)
- [ ] Log everything: attendance rate, engagement, replay views, pipeline notes

**Gate:** Follow-up sent within 24 hours, engagement segments routed, survey out.

### Step 7: Measure and Decide Next
- [ ] Metrics: registrations, attendance rate, cost per attendee, pipeline influenced, replay consumption
- [ ] Attendance-rate benchmark: compare against your own running average, not external stats
- [ ] Decide: repeat the format, kill it, or iterate the topic — every event should end in one of these three decisions
- [ ] Virtual vs in-person review: cost per meaningful conversation, not per attendee (heuristic)

**Gate:** Post-event report written with a repeat, kill, or iterate decision.

## Practitioner Grounding & Decision Rules

Built from GTM practice (Lenny Rachitsky's event-led growth interviews) + PESO handoff (Dietrich). Full research: practitioner-intelligence/syntheses/pr-launches.md, gtm.md.

- **Events are demand capture + relationship, not brand by default** (Rachitsky — HEURISTIC, T1): measure them against pipeline, not impressions.
- **Follow-up is the event** (synthesis — HEURISTIC, T2): most event ROI is lost in the 72 hours after.

Decision rules:
1. IF an event/webinar has no pipeline tracking (UTM + CRM source) THEN add it before promotion (Rachitsky — HEURISTIC, T1).
2. IF the post-event follow-up plan doesn't exist THEN build it before the event — the 72-hour window decides ROI (synthesis — HEURISTIC, T2).
3. IF owned/shared surfaces are weak THEN fix them first — events amplify, they don't create (Dietrich — FRAMEWORK, T1).
4. IF choosing format THEN match to goal: webinars for education/nurture, in-person for relationship/enterprise, AMAs for community (synthesis — HEURISTIC, T2).

## Metrics

- **Pipeline influenced per event** (Rachitsky — HEURISTIC, T1).
- **Attendee → follow-up → meeting conversion** in the 72-hour window (synthesis — HEURISTIC, T2).

## Sources

1. Lenny Rachitsky, GTM/event-led growth interviews | lennysnewsletter.com | tier 1 | 2026-08-15
2. Gini Dietrich, *Spin Sucks* (PESO) | spinsucks.com | tier 1 | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Format fit | Default webinar | Format matched to goal | Format + topic validated against ICP |
| Run of show | Loose agenda | Timed agenda | Timed, rehearsed, with interaction beats |
| Funnel | Form on a page | Landing + confirmation | Full funnel with tracking and reminders |
| Promotion | One email blast | Multi-channel | Speaker-led + community + final-72h push |
| Follow-up | Replay link | Segmented emails | Sales routing + survey + report |

### Common Failure Modes
- Picking the topic the company wants to talk about instead of what the audience wants to learn
- Speakers selling for 40 minutes — attendees leave and never return
- Skipping the hour-before reminder — it moves attendance more than any other single send (practitioner consensus, verify with your data)
- No producer, so the speaker juggles tech, chat, and content
- Treating non-attendees as lost — replays routinely outperform live attendance over time
- No repeat-or-kill decision, so mediocre events run forever
