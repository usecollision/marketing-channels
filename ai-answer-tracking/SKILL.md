---
name: ai-answer-tracking
category: ai-search
description: Monitor how AI engines answer brand queries - share-of-voice, sentiment, and competitive displacement alerts.
triggers:
  - "track AI answers"
  - "AI share of voice"
  - "monitor ChatGPT mentions"
  - "AI sentiment"
  - "competitive displacement"
  - "how does AI describe us"
  - "AI brand monitoring"
  - "share of voice in AI"
inputs:
  - brand_name
  - competitor_names
  - query_set
  - tracking_cadence
  - alert_recipients
outputs:
  - tracking_dashboard
  - share_of_voice_report
  - sentiment_trend_log
  - displacement_alerts
  - weekly_briefing
related_skills:
  - ai-search-audit
  - ai-citation-acquisition
  - entity-optimization
  - marketing-intelligence/social-listening
  - marketing-intelligence/competitor-battlecards
  - marketing-optimize/metrics-framework
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
  - mcp:ai-query
version: 1.0.0
---

## When to Use

Invoke when:
- You want ongoing visibility into how AI engines answer questions about your brand
- A one-off audit exists but you need a recurring measurement program over time
- Competitors are displacing you in AI answers and you need early warning
- You need to measure share of voice across ChatGPT, Perplexity, Claude, and Gemini
- Sentiment or accuracy of AI answers about your brand needs monitoring and alerting
- You must report AI visibility trends to leadership alongside classic SEO metrics

## Workflow

### Step 1: Define the Measurement Universe
Fix what gets tracked before building any tooling:

- [ ] Lock a query set mirroring how your ICP asks about you - brand, category, problem, comparison, and recommendation intents
- [ ] Fix the AI surfaces to track (start with ChatGPT, Perplexity, Claude, Gemini; expand as needed)
- [ ] Fix the competitor set you are benchmarking against - keep it stable so share-of-voice trends are comparable
- [ ] Define the metrics: mention rate, position, sentiment, recommendation rate, citation rate, and accuracy
- [ ] Agree a baseline snapshot before changes so you can measure movement

**Gate:** A frozen query set, surface list, competitor list, and metric definitions with a baseline captured.

### Step 2: Build the Capture Loop
Turn one-off checks into a repeatable measurement system:

- [ ] Automate or semi-automate query capture on a fixed cadence (weekly is a reasonable starting heuristic; tighten for fast-moving categories)
- [ ] For each response, record mention (Y/N), position, sentiment (positive/neutral/negative), recommendation (Y/N), and cited source
- [ ] Capture the raw answer text for later re-scoring - AI responses are non-deterministic, so store evidence, not just scores
- [ ] Normalize results into a structured log or sheet with query, surface, date, brand, and outcome columns
- [ ] Note model/version and any cited URLs so changes can be traced to a cause

**Gate:** A working capture loop producing structured, time-stamped records with raw answer evidence retained.

### Step 3: Share-of-Voice Measurement
Compute who wins each query and how that shifts over time:

- [ ] For each query, determine the winner (brand mentioned, recommended, or positioned first) and log per-surface and aggregated
- [ ] Calculate share of voice as your brand's share of mentions and recommendations vs the competitor set (heuristic metric - document your formula)
- [ ] Track the trend over time, not just the point-in-time value - direction matters more than any single reading
- [ ] Segment by intent - brand queries should be near-total yours; category and comparison queries are the real battleground

**Gate:** A share-of-voice score per query and per surface, tracked as a time series.

### Step 4: Sentiment & Accuracy Monitoring
Watch how you are described, not just whether you appear:

- [ ] Classify sentiment per mention and track the distribution over time
- [ ] Flag inaccuracies - wrong pricing, features, positioning, or stale facts - and log the claimed source
- [ ] Score accuracy per brand mention; wrong information is worse than no mention
- [ ] Correlate sentiment shifts with your own events (launches, pricing changes, PR) to understand what drives the narrative

**Gate:** A sentiment trend log and an accuracy register tracking incorrect claims and their apparent sources.

### Step 5: Displacement Alerts & Response
Get early warning when a competitor takes your place:

- [ ] Define displacement - a competitor replacing you in a recommendation, or your mention rate dropping below a threshold on a key query
- [ ] Set alert triggers on the highest-value queries (money queries) at a tighter threshold than long-tail ones
- [ ] Route alerts to owners with a response playbook - investigate the cause, check citations, and feed fixes back
- [ ] When displaced, diagnose: did your content go stale, did a competitor publish a study, or did entity data drift?
- [ ] Wire fixes into ai-citation-acquisition (new assets) and entity-optimization (correct entity data)

**Gate:** Alert rules live on key queries, with owners assigned and a diagnosis-to-fix loop documented.

### Step 6: Reporting & Operating Cadence
Make the program legible and durable:

- [ ] Build a dashboard showing share of voice, sentiment, and accuracy trends per surface and per query segment
- [ ] Produce a lightweight weekly or monthly briefing summarizing movement and flagging displacements
- [ ] Add AI visibility as a standing KPI alongside organic search in leadership reporting
- [ ] Re-baseline quarterly as queries, competitors, and models change - but version the baseline so trends stay comparable

**Gate:** A recurring report owned by one person, with AI share of voice embedded in the standard metrics stack.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Measurement universe | Ad hoc | Defined | Frozen + versioned baseline |
| Capture loop | Manual, sporadic | Semi-automated | Automated with raw evidence retained |
| Share of voice | No score | Point-in-time | Time series by query and surface |
| Sentiment/accuracy | Not tracked | Tracked | Trended + accuracy register |
| Alerts | None | Manual checks | Threshold alerts with owner + response loop |
| Reporting | None | Occasional | Standing cadence embedded in metrics |

### Common Failure Modes
- Changing the query or competitor set mid-stream, making trends incomparable
- Recording only scores and discarding the raw answer text, so you cannot re-check or audit
- Reading non-deterministic AI responses as noise and missing real, persistent shifts
- Alerting on everything and causing alert fatigue instead of focusing on money queries
- Ignoring accuracy - a confident wrong answer about your pricing does active damage
- Tracking mentions without a response playbook, so displacement is observed but never fixed
