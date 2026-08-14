---
name: newsjacking
category: pr
description: Hijack breaking news for coverage - monitoring setup, rapid-response commentary framework, safe vs risky hooks, and a speed-of-response playbook.
triggers:
  - "newsjacking"
  - "breaking news"
  - "rapid response"
  - "trend commentary"
  - "news monitoring"
  - "jump on the news"
inputs:
  - monitoring_feeds
  - brand_position
  - commentary_angle_options
  - response_time_budget
outputs:
  - monitoring_setup
  - story_triage_rules
  - commentary_draft
  - distribution_plan
  - risk_assessment
related_skills:
  - pr-strategy
  - press-pitching
  - press-release
  - marketing-intelligence/social-listening
  - marketing-intelligence/trend-detection
  - marketing-messaging/messaging-hierarchy
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- A breaking story in your category is moving and your company has a relevant point of view
- You want a standing rapid-response capability instead of ad hoc reactions
- Competitors consistently get quoted on stories where you are the better source
- A news cycle creates a window where your audience is newly receptive to your message
- Note: newsjacking is a supplement, not a strategy — it feeds on a narrative that already exists (see pr-strategy)

## Workflow

### Step 1: Set Up Monitoring
- [ ] Feeds: Google Alerts on category keywords, X lists of beat journalists, RSS of trade publications, newsletters, Slack news channels
- [ ] Assign a triage owner with clear coverage windows — someone must be watching during business hours
- [ ] Build the keyword list from your narrative: category terms, competitor names, regulation, platform changes
- [ ] Set escalation rules: what counts as "wake the team" vs "note and move on"

**Gate:** Monitoring live with a named owner, keyword list, and escalation rules.

### Step 2: Triage the Story
- [ ] Relevance test: is this our category? Does our audience care? Can we add facts, data, or an expert view? Is the story still developing?
- [ ] Safe hooks: category trends, new data, platform or regulatory changes, market moves — anything where you have genuine expertise
- [ ] Risky hooks (avoid): tragedies and disasters, active litigation involving others, political fights outside your lane, competitors' bad news — gloating reads terribly
- [ ] Speed check: stories have a half-life — commentary hours after the peak lands nowhere
- [ ] Score relevance x asset readiness x risk; proceed only on clear wins

**Gate:** Written go/no-go with the risk call documented for the record.

### Step 3: Pick the Response Angle
- [ ] Framework options: agree + evidence ("this trend is real, here are our numbers"), contrarian + data ("everyone is wrong, here is why"), explainer ("what this actually means"), prediction ("what happens next")
- [ ] Anchor the angle to your existing narrative — the news is the door, the narrative is the room
- [ ] One sentence only: if you cannot state the point in one sentence, you are not ready
- [ ] Prepare the proof: a stat, a chart, a customer story — commentary without proof is noise
- [ ] Pre-arrange legal and comms review for high-stakes topics

**Gate:** One-sentence angle with supporting proof and an approved risk posture.

### Step 4: Produce Fast
- [ ] Speed tiers (heuristics, calibrate to your team): expert comment within ~2 hours of the story breaking; data-backed take within a day; long-form analysis within 48 hours
- [ ] Pre-build assets: quote templates, data dashboards, chart templates so production is assembly, not creation
- [ ] Write the commentary: 2-3 paragraphs for pitches, a short social post, optionally a blog post for the long form
- [ ] Put the news hook in the first line — journalists skimming must see relevance instantly

**Gate:** Commentary produced within the tier deadline and reviewed by the designated approver.

### Step 5: Distribute
- [ ] Pitch journalists already covering the story (press-pitching list, filtered to this beat) — they need sources now, which is exactly your leverage
- [ ] Post on X and LinkedIn with the news hook; tag nobody gratuitously
- [ ] Publish the long form to the blog and link from the short posts
- [ ] Respect the journalist's deadline — offer phone availability immediately, not next week
- [ ] Monitor replies and be ready for follow-up questions

**Gate:** Distribution completed within the story's active window, with pitches sent to on-story journalists.

### Step 6: Debrief and Refine
- [ ] Log: response time from alert to publish, who picked it up, referral traffic, new journalist relationships
- [ ] Compare speed tiers to actual pickup — tighten where you missed the window
- [ ] Update the keyword list and escalation rules from what the cycle taught you
- [ ] Feed angles that worked back into the pr-strategy angle bank

**Gate:** Debrief written and at least one playbook improvement shipped.

## Practitioner Grounding & Decision Rules

Practitioners: David Meerman Scott (newsjacking originator — T2), Gini Dietrich (PESO context — T2), Ed Zitron (pitch discipline — T2).

- IF a story breaks in your market AND you have a legitimate tie THEN publish a credible take within hours — newsjacking only works in real time; "now doesn't mean tomorrow, it means now" (Meerman Scott, FRAMEWORK, T1).
- IF you have no legitimate tie to the story THEN skip — credibility is the gate; forced newsjacking is tone-deaf (Meerman Scott, FRAMEWORK, T2).
- IF the story is >24h old THEN treat it as evergreen content, not newsjacking (Meerman Scott, HEURISTIC, T2).
- IF your org can't approve/publish within ~4h THEN build crisis-speed approval before relying on newsjacking (Meerman Scott, HEURISTIC, T2).
- IF monitoring only your trade press THEN add the wider sphere — monitor both your immediate market and global news for opportunities (Meerman Scott, FRAMEWORK, T1).
- IF you publish the take THEN make it liftable: keyword-of-the-moment headline + second-paragraph facts journalists can cite (Meerman Scott, TACTIC, T1).
- IF newsjacking attempts get 0 pickups 3 times THEN stop forcing it — no legitimate tie exists (synthesis, HEURISTIC, T2).

## Metrics

- Primary: newsjacked-piece pickup rate; inbound journalist inquiries; coverage share of voice during the news cycle.
- Guardrails: time-to-publish after story break (<4h), keyword-of-the-moment visibility, tie legitimacy score (must pass before publishing).
- Timebox: per breaking story; review monthly pickup rate.
- When to re-measure: 3 failed attempts = kill the lane and rebuild tie/monitoring infrastructure first.

## Sources

1. Meerman Scott, "Newsjacking!" | https://www.davidmeermanscott.com/blog/2011/11/newsjacking.html | T1 | 2026-08-15
2. Meerman Scott, Newsjacking book excerpt | https://www.davidmeermanscott.com/hubfs/documents/Newsjacking-free-excerpt.pdf | T1 | 2026-08-15
3. Synthesis: syntheses/pr-launches.md (§Newsjacking conditions/failure knowledge) | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Relevance | Stretch connection | Category-adjacent | Direct expertise + new facts |
| Risk | Red lines ignored | Risk noted | Risk assessed and documented |
| Speed | Days later | Same day | Within the speed-tier deadline |
| Proof | Opinion only | One stat | Data, chart, or customer evidence |
| Pickup | None logged | Some shares | Journalist quotes + traffic logged |

### Common Failure Modes
- Reacting to everything — rapid-response fatigue burns the team and the audience
- Jumping on tragedies or litigation for clicks — reputational damage outweighs any win
- Commentary with no data: journalists already have opinions, they need evidence
- Speed without review: a rushed hot take becomes the story about you
- Treating newsjacking as the whole PR strategy instead of a spike on top of a narrative
