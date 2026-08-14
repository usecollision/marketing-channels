---
name: press-release
category: pr
description: Write and distribute press releases - newswire format, headline structure, inverted pyramid, boilerplate, and distribution timing.
triggers:
  - "press release"
  - "newswire"
  - "write an announcement"
  - "media advisory"
  - "boilerplate"
  - "funding announcement"
inputs:
  - announcement_facts
  - executive_quotes
  - launch_date
  - distribution_budget
outputs:
  - press_release_draft
  - boilerplate_block
  - distribution_plan
  - supporting_assets_list
related_skills:
  - pr-strategy
  - press-pitching
  - newsjacking
  - product-launch-playbook
  - marketing-messaging/brand-voice
  - marketing-messaging/value-proposition
required_context:
  - .context/product-marketing.md
allowed_tools: []
version: 1.0.0
---

## When to Use

Invoke when:
- A genuinely newsworthy event needs a formal written announcement (funding, launch, partnership, major hire, data release)
- Distributing via newswire services or syndication channels that require standard format
- Journalists request a release or media kit as background material
- Maintaining a newsroom page that documents company milestones
- Note: not every announcement needs a release — a direct pitch often outperforms (see press-pitching)

## Workflow

### Step 1: Confirm the News and Pick the Format
- [ ] Kill criteria — skip the release if: it only matters internally, no third party would cover it, or it is a minor feature update
- [ ] Format options: press release (formal, distributable), media advisory (short invite to an event or briefing), pitch-only (personal email, no release)
- [ ] Confirm the one core fact a reader should remember and write it in one sentence

**Gate:** One core-fact sentence plus an explicit format decision with rationale.

### Step 2: Write Headline and Subheadline
- [ ] Headline: active voice, names the news, uses a number or concrete outcome when one exists
- [ ] Keep under ~80 characters (heuristic; long headlines truncate on newswires)
- [ ] Avoid internal jargon, product codenames, and adjectives that carry no information
- [ ] Subheadline (1-2 sentences): adds the why-it-matters context the headline can't carry
- [ ] Write 3 headline options and pick the most specific

**Gate:** Headline under 80 characters that a stranger can repeat back, plus a context-adding subheadline.

### Step 3: Write the Inverted-Pyramid Body
- [ ] Paragraph 1: who, what, when, where, why — a reader who stops here still got the news
- [ ] Paragraphs 2-3: context and significance — market trend, customer problem, what this enables
- [ ] Quotes: executive quote near the top; customer or partner quote mid-release; every quote adds information, not enthusiasm
- [ ] Numbers: every stat attributed to a source or timeframe ("grew X% over 12 months, per internal data")
- [ ] Keep the whole release ~300-500 words (heuristic) — journalists skim for facts
- [ ] Include one link to more detail (announcement page, not a generic homepage)
- [ ] Avoid forward-looking promises you cannot support

**Gate:** A reader who reads only the first paragraph can state the news; all numbers attributed.

### Step 4: Add Boilerplate and Media Info
- [ ] Boilerplate block at the end: what the company does, for whom, one credibility marker, website link
- [ ] Media contact: name, title, email, phone for interviews
- [ ] Multimedia: links to logos, product screenshots, founder headshots, data charts (if applicable)
- [ ] "About [Company]" section doubles as the boilerplate for future releases — keep it current
- [ ] Include the release date and city at the top, per newswire convention

**Gate:** Complete boilerplate plus media contact and multimedia links present.

### Step 5: Plan Distribution and Timing
- [ ] Channel decision: newswire (reach and syndication, costs money), direct pitch (targeted, higher conversion), or hybrid
- [ ] Newswire timing conventions: distribute Tuesday-Thursday, early morning in the target time zone, avoiding holidays (industry convention, verify with provider)
- [ ] Align release time with the embargo and with press-pitching outreach — pitch goes out first
- [ ] Owned channels: publish to newsroom and blog, email list, social on release day with a human voice, not a copy-paste
- [ ] Prepare spokespeople with the release and anticipated questions before distribution

**Gate:** Distribution plan with channel choice, timing, and owner per channel.

### Step 6: Measure and Follow Up
- [ ] Track: pickup and syndication, referral traffic to the announcement link, backlinks, brand search lift, interview requests
- [ ] Follow up A-tier journalists who were pitched but silent — day +3, short note with the release link
- [ ] Log every outlet that covered the news in the media CRM
- [ ] Archive the release in the newsroom with correct metadata (date, category, tags)

**Gate:** Pickup logged, referral traffic captured, and follow-up completed for all A-tier targets.

## Practitioner Grounding & Decision Rules

Built from Gini Dietrich (PESO model), David Meerman Scott (newsjacking, real-time marketing), Ed Zitron (journalist reality). Full research: practitioner-intelligence/syntheses/pr-launches.md.

- **PESO handoff order** (Dietrich — FRAMEWORK, T1): owned and shared media must exist before earned (press) — journalists check your surfaces.
- **Newsjacking window is hours** (Meerman Scott — EMPIRICAL, T1): second-paragraph content on a credible tie, published within hours, or skip.
- **Journalists get ≤150 words, plain text, one relevant reason** (Zitron — HEURISTIC, T1).

Decision rules:
1. IF owned/shared surfaces don't exist THEN build them before pitching (Dietrich — FRAMEWORK, T1).
2. IF a story breaks in your market with a credible tie THEN newsjack within hours — second-paragraph placement; if you can't publish fast, skip (Meerman Scott — EMPIRICAL, T1).
3. IF pitching a named journalist THEN ≤150 words, plain text, one relevant reason; volume only for tier-3/long-tail (Zitron — HEURISTIC, T1).
4. IF a release lacks an angle a journalist could repurpose THEN rewrite — newswire format is not a substitute for news value (Meerman Scott — FRAMEWORK, T1).

## Metrics

- **Pickup rate** per release + per angle (Dietrich — HEURISTIC, T1).
- **Newsjack speed**: hours from story to publish (Meerman Scott — EMPIRICAL, T1).
- **Share-of-voice vs target publications** (Dietrich — FRAMEWORK, T1).

## Sources

1. Gini Dietrich, *Spin Sucks* (PESO model) | spinsucks.com | tier 1 | 2026-08-15
2. David Meerman Scott, *Newsjacking* + real-time marketing | davidmeermanscott.com | tier 1 | 2026-08-15
3. Ed Zitron, media/press reality (EZPR) | ezpr.com / his podcast | tier 2 | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Newsworthiness | Internal update | Audience-relevant | Third party would cover it unprompted |
| Headline | Vague, jargony | Clear | Specific, repeatable, under 80 chars |
| Structure | Chronological ramble | Inverted pyramid | First paragraph = complete news |
| Quotes | Generic enthusiasm | Informative | Each quote adds a fact or angle |
| Completeness | Missing boilerplate or media info | Boilerplate present | Boilerplate + media contact + multimedia |

### Common Failure Modes
- Writing a release for news that isn't news — burns credibility with journalists
- Burying the actual news in paragraph four
- Quotes that say "we are thrilled" and nothing else
- Distributing before the pitched journalists have been told — kills the relationship
- Unattributed numbers that journalists must chase down or drop
- Treating newswire syndication as earned coverage in reports
