---
name: social-strategy
category: social
description: Build a cross-platform social media strategy aligned to growth goals and ICP presence.
triggers:
  - "social media strategy"
  - "social content plan"
  - "which platforms should we be on"
  - "grow our social"
  - "social media plan"
inputs:
  - product_context
  - icp
  - current_social_presence
  - content_pillars
outputs:
  - platform_strategy
  - content_calendar
  - growth_tactics
  - engagement_playbook
related_skills:
  - linkedin-content
  - x-threads
  - marketing-messaging/content-strategy
  - marketing-messaging/conversion-copywriting
required_context:
  - .context/product-marketing.md
allowed_tools: []
version: 1.0.0
---

## When to Use

Invoke when:
- Starting social from zero and choosing platforms
- Social presence exists but growth is stagnant
- Need to align social with content and business goals
- Expanding to new platforms
- Building personal brand strategy for founders/team

## Workflow

### Step 1: Platform Selection
Match platforms to where your ICP actually spends time:

| Platform | Best For | Content Type | Effort | Your ICP Here? |
|----------|----------|-------------|--------|----------------|
| LinkedIn | B2B, professional, thought leadership | Text posts, carousels, articles | Medium | |
| X/Twitter | Tech, SaaS, real-time, communities | Threads, takes, engagement | High | |
| Reddit | Niche communities, authentic discussion | Value-first comments, AMAs | Medium | |
| TikTok | Gen Z/Millennial, visual, viral | Short video, trends, education | High | |
| YouTube | Long-form education, tutorials, SEO | Videos, Shorts | Very High | |
| Instagram | Visual brands, DTC, lifestyle | Reels, Stories, carousels | High | |

Rule: Start with 1-2 platforms max. Master them before expanding.

**Gate:** 1-2 primary platforms selected with ICP-alignment evidence.

### Step 2: Content Pillars for Social
Adapt your content pillars to social formats:

| Pillar | LinkedIn Format | X Format | Reddit Format |
|--------|---------------|----------|---------------|
| [Pillar 1] | Personal story + lesson | Thread with data | Comment in relevant sub |
| [Pillar 2] | Carousel how-to | Hot take + proof | Detailed answer |
| [Pillar 3] | Case study breakdown | Quick tip | Resource share |

Content mix (per week):
- 40% Educational (teach something valuable)
- 30% Personal/Story (build connection)
- 20% Engagement (questions, polls, discussions)
- 10% Promotional (product, launches, offers)

**Gate:** Content pillars translated to platform-native formats with weekly mix defined.

### Step 3: Growth Mechanics
For each platform, define growth levers:

**LinkedIn:**
- Comment on 10 relevant posts/day before posting
- Engage with ICP's content consistently
- Post at peak hours (Tu-Th, 8-10am)
- Use hooks in first line (no "I'm excited to announce...")
- Tag relevant people sparingly and genuinely

**X/Twitter:**
- Reply to large accounts in your niche (add value, not "great post!")
- Thread 2x/week (threads get 10x the reach of single tweets)
- Quote tweet with hot takes
- Build in public (share progress, numbers, learnings)
- Engage in Spaces

**Reddit:**
- Provide genuine value for 2-4 weeks before any promotion
- Become a known contributor in 3-5 subreddits
- Answer questions thoroughly (top answers get upvoted for years)
- Never be obviously promotional (instant ban)

**Gate:** Platform-specific growth tactics defined with daily/weekly actions.

### Step 4: Content Calendar
Weekly publishing rhythm:

| Day | Platform 1 (LinkedIn) | Platform 2 (X) |
|-----|----------------------|-----------------|
| Mon | Personal insight | Thread |
| Tue | How-to/educational | 3-5 value tweets |
| Wed | Engagement post (question/poll) | Quote tweets + takes |
| Thu | Case study/result | Thread |
| Fri | Industry take/opinion | Recap or fun |

**Gate:** 2-week calendar filled with specific topic + format assignments.

### Step 5: Measurement
Track what matters per platform:

| Metric | LinkedIn | X | Reddit |
|--------|----------|---|--------|
| Growth | Followers, connection requests | Followers, profile visits | Karma, sub reputation |
| Engagement | Comments, shares, saves | Replies, retweets, bookmarks | Upvotes, replies |
| Conversion | Profile → website clicks, DMs | Link clicks, DMs | Traffic from comments |
| Content | Impressions per post, top posts | Impressions, thread performance | Top comments |

Review weekly. Double down on what works. Kill what doesn't.

**Gate:** Metrics defined with weekly review cadence.

## Practitioner Grounding & Decision Rules

Built from Justin Welsh, Richard van der Blom (1.3M-post LinkedIn dataset), Nicolas Cole, David Spinks/Rich Millington (community). Full research: practitioner-intelligence/syntheses/social.md.

- **Reach is baseline + performance + luck** (van der Blom — EMPIRICAL, T1-as-reported): ~50% baseline norm, 29.5% post performance, 20.5% luck; posts at 4x your own norm get +639% reach. Compare against your own baseline, not absolutes.
- **Format = job** (van der Blom — EMPIRICAL, T1): images/long-form reach new audiences (47-52% out-of-network); polls/reposts/live deepen existing (72-76%).
- **Pods, comment-and-run, deletion, DM spam are penalized** (van der Blom — EMPIRICAL, T1): engagement pods detected at 97%; ghosted replies cost −35% comment reach.
- **Pick the platform by audience location, not trend** (Cole — HEURISTIC, T1).

Decision rules:
1. IF no primary platform THEN pick one by where the ICP actually is — B2B → LinkedIn first (Welsh); developer/technical → Reddit presence non-optional (SEL study); consumer/visual → IG/TikTok (Cole — HEURISTIC, T1).
2. IF the goal is new audience THEN use out-of-network-skewing formats (images, long-form, articles); IF deepening existing THEN polls, reposts, live (van der Blom — EMPIRICAL, T1).
3. IF a post underperforms THEN compare to your own baseline norm before concluding anything — reach is mostly baseline + luck (van der Blom — EMPIRICAL, T1).
4. IF running engagement pods or comment-and-run THEN stop — pattern-detected and penalized (van der Blom — EMPIRICAL, T1).
5. IF building community THEN define purpose + 3 value behaviors before choosing tools (Millington — FRAMEWORK, T1).

## Metrics

- **Reach vs your own baseline norm** (4x-norm = standout) (van der Blom — EMPIRICAL, T1).
- **Out-of-network vs existing-audience share per format** (van der Blom — EMPIRICAL, T1).
- **Community**: value behaviors per member (not member count) (Millington — FRAMEWORK, T1).

## Sources

1. Richard van der Blom, LinkedIn algorithm research (1.3M posts) | linkedin.com/in/richardvanderblom | tier 1 | 2026-08-15
2. Justin Welsh, LinkedIn systems | his LinkedIn/X | tier 2 | 2026-08-15
3. Nicolas Cole, platform selection + writing systems | Ship 30 for 30 | tier 2 | 2026-08-15
4. Rich Millington, community purpose/behaviors (FeverBee) | feverbee.com | tier 1 | 2026-08-15
5. Search Engine Land, 117-brand Reddit study | searchengineland.com | tier 1 | 2026-08-15

## Evaluation & QA

### Common Failure Modes
- Being on too many platforms (diluted effort, mediocre everywhere)
- Posting without engaging (social is social — talk to people)
- Corporate voice on personal platforms (especially LinkedIn, X)
- All promotional, no value (the 90/10 rule exists for a reason)
- Inconsistency (posting for 2 weeks then ghosting for a month)
- Not adapting content to platform format (same post everywhere)