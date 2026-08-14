---
name: youtube-strategy
category: social
description: Build a YouTube channel strategy - niche selection, video SEO, packaging, and retention mechanics.
triggers:
  - "YouTube strategy"
  - "YouTube channel"
  - "video SEO"
  - "YouTube thumbnails"
  - "video titles"
  - "Shorts strategy"
  - "YouTube growth"
  - "audience retention"
inputs:
  - product_context
  - icp
  - existing_video_assets
  - competitors_channels
outputs:
  - channel_thesis
  - format_portfolio
  - video_seo_checklist
  - packaging_guide
  - retention_playbook
  - content_pipeline
related_skills:
  - content-calendar
  - social-strategy
  - linkedin-content
  - marketing-messaging/video-scripts
  - marketing-intelligence/trend-detection
  - marketing-intelligence/customer-research
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Deciding whether YouTube is worth the production investment for your ICP
- Launching or relaunching a channel without a niche thesis
- Videos get impressions but no clicks, or clicks but no watch time
- Need a repeatable format system instead of one-off uploads
- Repurposing existing content (webinars, tutorials, talks) into a channel

## Workflow

### Step 1: Niche & Channel Positioning
- [ ] Define the audience-ICP overlap: which of your customers are actually on YouTube, watching what?
- [ ] Run a content-gap analysis: search core topics, study the top channels' formats, find underserved angles
- [ ] Write the channel thesis in one sentence: who it's for + what transformation each video delivers
- [ ] Set the business job of the channel honestly: trust, demand capture, education, or support — not all four at once
- [ ] Decide commitment level: a channel is a quarters-long play; half-committed uploads lose to nobody

**Gate:** One-sentence channel thesis written; gap analysis shows a real angle you can serve better.

### Step 2: Format Portfolio
- [ ] Inventory viable long-form formats: how-to, review, case study, interview, listicle, vlog, deep-dive
- [ ] Assess Shorts role: discovery flywheel vs diluted effort — decide explicitly
- [ ] Pick 2-3 core formats max; consistency in format builds returning viewers (heuristic from channel case studies)
- [ ] Design series/playlists: repeatable structures (e.g. "Tool Teardown Tuesdays") that compound
- [ ] Rate capacity: real production hours per format vs calendar commitment (see content-calendar)

**Gate:** Format portfolio locked with 2-3 core formats, series names, and a production-capacity check.

### Step 3: Video SEO
- [ ] Keyword research for YouTube: autocomplete, competitors' top videos, related searches, search-volume tools
- [ ] Titles: natural-language phrasing with the primary phrase early; length fits mobile display
- [ ] Descriptions: first 2 lines carry the hook and keywords; add chapters, links, and timestamps
- [ ] Tags: minor weight (assumption — widely reported as low-signal; spend seconds, not minutes)
- [ ] Upload accurate captions/subtitles — transcripts feed indexing and accessibility
- [ ] Cards and end screens: route to next video in the series and subscribe

**Gate:** Every upload passes the video SEO checklist before publish.

### Step 4: Packaging — Titles & Thumbnails
- [ ] CTR mechanics: curiosity + clarity; the promise of the title must be delivered in the first minute
- [ ] Title patterns: number + outcome, "how to X without Y", transformation framing — test across your formats
- [ ] Thumbnail rules (heuristics): one focal point, readable contrast, max ~3 words, faces with emotion outperform plain objects
- [ ] Test & compare: run A/B thumbnails (YouTube's test feature) on underperforming videos
- [ ] Ban clickbait mismatch: a click that bails in 15 seconds trains the algorithm against you

**Gate:** Packaging guide written per format; thumbnail A/B testing active on videos underperforming impressions.

### Step 5: Retention Mechanics
- [ ] Hook design: first 15-30 seconds state the promise and the payoff — no intros, no logos
- [ ] Edit for pace: cut dead air, hold shots under ~5 seconds unless deliberately slow (heuristic)
- [ ] Pattern interrupts: scene changes, zooms, b-roll, on-screen text to reset attention every ~30 seconds
- [ ] Payoff management: open loops ("by the end you'll know X") and deliver them on schedule
- [ ] Study your retention graph: find the drop-off points and re-edit future videos to eliminate them
- [ ] End with a concrete next step: next video, comment prompt, or off-YouTube action

**Gate:** Retention playbook written from your own analytics, not generic advice; every video reviewed against its retention graph.

### Step 6: Distribution & Measurement
- [ ] Embed videos in site content and help docs; feed clips to Shorts, social, and newsletters (content-calendar cascade)
- [ ] Track the metrics that matter: CTR, average view duration, retention %, subs per view, then site clicks/conversions
- [ ] Monthly review: which format/topic pairs earn watch time AND business value; kill or rework the rest
- [ ] Iterate packaging on old videos — thumbnails and titles are cheap changes with real CTR upside
- [ ] Reassess channel thesis quarterly against the gap analysis

**Gate:** Monthly channel scorecard live; packaging iterations and format decisions logged with evidence.

## Practitioner Grounding & Decision Rules

Practitioners: Tim Schmoyer (Video Creators — retention analytics, T2), Derral Eves (The YouTube Formula — packaging, T2), Roberto Blake (content operations, T3).

- IF the retention graph shows a repeated drop point THEN find and cut the trigger (one channel lost viewers every time the word "module" was said; removing it flattened the graph) (Schmoyer, EMPIRICAL, T2).
- IF CTR is low but retention is fine THEN fix packaging (title + thumbnail), not content — packaging decides whether retention ever gets a chance (Eves/Schmoyer, HEURISTIC, T2).
- IF the channel lacks a consistent schedule THEN establish one before scaling production — consistency trains YouTube's suggestion system (Schmoyer, HEURISTIC, T2).
- IF you can't state why viewers should care (vs 500+ hours uploaded per minute) THEN answer that before producing more (Schmoyer, HEURISTIC, T2).
- IF analytics show a winning video type THEN make more like it; don't chase unrelated trends (Schmoyer, HEURISTIC, T2).
- IF making a video that teaches a one-time task THEN reframe to make the audience FEEL something — channels win on feeling, not DIY utility (Schmoyer, HEURISTIC, T2).
- IF thumbnails/titles are un-tested THEN A/B test packaging before investing in production (Eves, FRAMEWORK, T2).
- IF 30s retention < 30% on long-form THEN shorten/restructure the intro — intros decide early drop-off (synthesis of Schmoyer/Eves, HEURISTIC, T2).

## Metrics

- Primary: audience retention % at 30s / 50% / end; watch time per view; CTR from impressions.
- Guardrails: suggested-traffic share, returning-viewer rate, drop-point consistency across videos.
- Timebox: 10-20 videos to establish retention baselines; re-measure per video after packaging changes.
- When to re-measure: after any intro/packaging change; if CTR < 2% or 30s retention < 30%, stop production and fix packaging first.

## Sources

1. Schmoyer interview, "How to Get Your Videos Discovered on YouTube" | https://www.socialmediaexaminer.com/how-to-get-videos-discovered-on-youtube-tim-schmoyer/ | T1 | 2026-08-15
2. Schmoyer, retention experiment | https://videocreators.com/my-experiment-to-boost-audience-retention/ | T1 | 2026-08-15
3. Schmoyer, "What Video Should You Make Next?" | https://videocreators.com/what-video-should-you-make-next-combining-analytics-with-experiments-to-keep-viewers-engaged/ | T1 | 2026-08-15
4. Eves, The YouTube Formula (packaging canon, T2 — not fetched this session) | 2026-08-15
5. Synthesis: syntheses/social.md (§YouTube) | 2026-08-15

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Positioning | No thesis | Vague niche | One-sentence thesis + gap analysis |
| Formats | Random uploads | Some formats | 2-3 core formats + series + capacity check |
| SEO | Titles guessed | Keywords researched | Full checklist applied per upload |
| Packaging | Stock thumbnails | Decent CTAs | Guide + A/B testing on underperformers |
| Retention | Ignored | Watched graph | Playbook from own data, iterated |

### Common Failure Modes
- Chasing views instead of serving the ICP — big audiences, zero business
- Clickbait titles that destroy retention and signal quality
- Inconsistent upload cadence; the algorithm rewards returning viewers, not bursts
- Ignoring the retention graph while obsessing over subscribers
- No series continuity — every video starts from scratch with viewers
- Measuring success in subscribers while the channel's job was demand capture
