---
name: podcast-appearances
category: pr
description: Get your founder on podcasts - show discovery, host pitch emails, episode prep, promo assets, and referral measurement.
triggers:
  - "podcast guest"
  - "podcast outreach"
  - "get on podcasts"
  - "podcast tour"
  - "guest appearances"
  - "founder interviews"
inputs:
  - founder_bio
  - story_angles
  - target_audience
  - promo_channel_inventory
outputs:
  - show_shortlist
  - pitch_emails
  - episode_prep_brief
  - promo_asset_pack
  - measurement_plan
related_skills:
  - pr-strategy
  - press-pitching
  - content-calendar
  - marketing-intelligence/customer-research
  - marketing-messaging/brand-voice
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Founder or executive is ready for a podcast tour as a growth channel
- Building brand awareness, credibility, and backlinks through long-form conversation
- Press coverage is hard to crack but niche shows are reachable
- You need a repeatable pipeline from discovery to pitch to booked episode
- A launch is coming and podcast appearances should precede it (see product-launch-playbook)

## Workflow

### Step 1: Define the Tour and Guest Positioning
- [ ] Goals: audience reach, credibility, backlinks, customer conversations — pick the primary one
- [ ] Guest one-liner: who you are, what you have built, what you believe — usable verbatim by a host
- [ ] 3-5 story angles: founding story, category contrarian take, data from your product, lessons learned, prediction
- [ ] Decide the tour shape: 10-15 episodes over 3 months is a realistic stretch for most founders (heuristic)
- [ ] Confirm the founder's time budget — recording, prep, and promotion per episode

**Gate:** Guest one-liner plus 3-5 story angles written and founder budget confirmed.

### Step 2: Discover Shows
- [ ] Search directories: Listen Notes, Apple Podcasts, Spotify by topic keywords; search the guest names of comparable founders
- [ ] Check competitor and peer founder histories — where did they appear in the last 2 years?
- [ ] Mine newsletters, X, and LinkedIn for hosts who actively seek guests
- [ ] Filter: active in the last ~90 days, audience matches your ICP, host does real interviews (not just promo swaps)
- [ ] Log per show: name, host, audience description, recent topics, contact path

**Gate:** 20-30 candidate shows logged with audience-fit notes (heuristic target; adjust to niche size).

### Step 3: Tier and Prioritize
- [ ] Score each show: audience relevance x reach x production quality x booking likelihood
- [ ] A-tier (5-8 shows): high fit, worth custom pitches and prep
- [ ] B-tier (10-15): solid fit, templated-but-personalized pitches
- [ ] C-tier: skip unless the host invites you — your time is the scarce input
- [ ] Sequence: book B-tier first to sharpen the pitch and get reps, then go after A-tier with episode links as proof (heuristic)

**Gate:** Tiered shortlist with a booking order and per-show pitch angle.

### Step 4: Pitch the Hosts
- [ ] Open with a reference to a specific recent episode — proves you actually listen
- [ ] One line on who you are and why their audience cares
- [ ] Offer 2-3 concrete episode ideas, not "I would love to come on"
- [ ] Credibility markers: product, numbers, prior appearances, media
- [ ] Follow-up cadence: +5 days nudge, +14 days final, then stop (heuristic); hosts are busy and inboxes are brutal
- [ ] One host per email, never a mass BCC list

**Gate:** Every pitch references a specific episode and offers 2-3 concrete episode ideas.

### Step 5: Prep the Episode
- [ ] Send the host a one-pager: bio, headshot, 5-8 talking points with hooks, 2-3 stories with numbers, suggested questions
- [ ] Founder prep: rehearse the 3 stories out loud, know the numbers cold, have one contrarian take ready
- [ ] Structure stories with stakes and resolution — rambling loses listeners fast
- [ ] Agree on the promo plan with the host (when it airs, how both sides promote)
- [ ] Technical prep: quiet room, decent mic, headphones — audio quality decides whether listeners stay

**Gate:** One-pager sent, founder rehearsed, promo plan agreed.

### Step 6: Promote and Repurpose
- [ ] On air date: post on X and LinkedIn with the episode link and the host tagged; send to the email list
- [ ] Repurpose: 2-3 short clips (audiograms), 1-2 quote cards, a summary post — one episode feeds a week of content
- [ ] Ask for the show-notes backlink to your site (most hosts will add one if asked)
- [ ] Thank the host publicly and privately; share their show with your audience

**Gate:** Episode promoted on all owned channels within 48 hours and a backlink requested.

### Step 7: Measure Referral Impact
- [ ] Tag every episode with a UTM or unique link so traffic is attributable
- [ ] Track: referral traffic per episode, brand search lift in the following weeks, backlinks won, demo or signup mentions, inbound requests from other hosts
- [ ] Cost per episode = founder hours + prep time; compare against other channels, not in absolute terms (heuristic framing)
- [ ] Quarterly: retire angles nobody books, double down on shows that converted

**Gate:** Per-episode attribution in place and at least one quarterly optimization made.

## Practitioner Grounding & Decision Rules

Built from podcast-guesting practice (Jordan Harbinger's outreach method) + PR discipline (Dietrich/Meerman Scott). Full research: practitioner-intelligence/syntheses/pr-launches.md.

- **The outreach doc matters more than the pitch** (Harbinger — HEURISTIC, T2): his show's public outreach guide (why this show, what you offer, proof of listening) is the canonical artifact.
- **Podcast appearances are an owned-asset multiplier** (Dietrich — FRAMEWORK, T1): clips and transcripts feed owned media.

Decision rules:
1. IF pitching a show THEN demonstrate specific listening (name episodes/topics), state what you offer the audience, and keep it under 150 words (Harbinger — HEURISTIC, T2).
2. IF the show's audience doesn't overlap the ICP THEN decline — reach without relevance (synthesis — HEURISTIC, T2).
3. IF an appearance is booked THEN plan clip/transcript repurposing before recording (Dietrich — FRAMEWORK, T1).
4. IF evaluating the channel THEN track qualified-referral pipeline, not downloads (synthesis — HEURISTIC, T2).

## Metrics

- **Qualified leads/referrals per appearance** (synthesis — HEURISTIC, T2).
- **Repurposed-asset yield** (clips, transcripts, posts) per episode (Dietrich — FRAMEWORK, T1).

## Sources

1. Jordan Harbinger, outreach guide + show practice | jordanharbinger.com | tier 2 | 2026-08-15
2. Gini Dietrich, *Spin Sucks* | spinsucks.com | tier 1 | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Positioning | "Thought leader" | One-liner + angles | One-liner + 3-5 angles with proof |
| Discovery | Big names only | Directories searched | Directories + peer history + community mining |
| Pitches | Mass template | Personalized | Specific episode + 2-3 episode ideas each |
| Prep | Wing it | Talking points | One-pager + rehearsed stories + tech check |
| Measurement | "It went well" | Links tracked | UTM attribution + backlinks + pipeline notes |

### Common Failure Modes
- Pitching shows you have never listened to — hosts can tell in the first line
- Chasing reach over relevance — a big show with the wrong audience produces zero pipeline
- Rambling episodes — unrehearsed stories burn the audience and the host's goodwill
- No promotion — hosts remember guests who brought an audience and rebook them
- Counting downloads you cannot see as results — measure what you own: referral traffic, backlinks, mentions
- Overloading the founder: three episodes a week burns the founder and dilutes quality
