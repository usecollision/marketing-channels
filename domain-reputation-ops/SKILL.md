---
name: domain-reputation-ops
category: outbound
description: Operate outbound sending domains at scale - secondary domain setup, rotation strategy, warmup infrastructure, safe volume scaling, and blacklist monitoring.
triggers:
  - "secondary domains"
  - "sending domain"
  - "domain rotation"
  - "blacklist"
  - "scale outbound"
  - "warmup infrastructure"
inputs:
  - primary_domain
  - send_volume_target
  - email_platform
  - deliverability_reports
outputs:
  - domain_inventory
  - rotation_policy
  - warmup_runbook
  - scaling_schedule
  - blacklist_monitor
related_skills:
  - email-deliverability
  - cold-email-sequence
  - multichannel-outbound
  - lead-sourcing-enrichment
  - newsletter-operations
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Scaling cold outbound past a few hundred emails a day
- Protecting the primary domain from outbound reputation risk
- Setting up secondary sending domains
- Recovering from a blacklist or spam-folder slide
- Planning warmup infrastructure for a growing team

## Workflow

### Step 1: Domain Architecture
- **Never cold-email from the primary domain** - outbound risk stays quarantined from product email, logins, and support
- **Secondary domain naming** - close variants of the brand (getbrand.com, brandhq.com, trybrand.com); must resolve and look legitimate to recipients and filters
- **Redirect behavior** - secondary domains 301-redirect the web root to the primary site so curious recipients land correctly
- **One purpose per domain** - outbound sales domains separate from newsletter domains where possible
- **Volume math** - work backward from the send target to domain count using per-domain send caps (common heuristics - roughly 30-50 sends/day per mailbox early, scaling with warmed reputation; treat as starting assumptions and adjust to observed placement)

**Gate:** Domain map showing purpose, volume ceiling, and redirect state per domain.

### Step 2: Secondary Domain Setup
For every secondary domain:

- Register the domain and add the standard DNS records (SPF, DKIM, DMARC per email-deliverability)
- Configure in the ESP with a dedicated tracking subdomain
- Set up mailboxes - multiple mailboxes per domain share the domain's reputation
- Add Google Postmaster Tools and Microsoft SNDS verification
- Redirect web root to the primary site
- Document ownership, registrar, and renewal dates

**Gate:** Every secondary domain passes authentication checks and appears in postmaster tooling.

### Step 3: Rotation Strategy
- **Rotation dimensions** - rotate by sequence (one domain per sequence), by rep (one domain per SDR), or by segment; pick based on blast radius when a domain dips
- **Health checkpoints** - review per-domain placement, complaint, and bounce rates weekly
- **Degradation rules** - a domain with falling placement goes to reduced volume, then rest, then retirement
- **Retirement policy** - retire quietly, do not delete; history and redirects stay
- **Never hide from recipients** - secondary domains must not disguise identity; that pattern looks like spam to filters and humans

**Gate:** Rotation policy written with health thresholds and degradation steps.

### Step 4: Warmup Infrastructure
- **Warmup tooling** - dedicated warmup services or native ESP warmup for each domain and mailbox
- **Ramp schedule** - per-domain volume starts low and steps up weekly (heuristic - 3-6 week ramp; see email-deliverability)
- **Engagement seeding** - warmup accounts reply/star to build positive signals; start real sends to the most engaged segments first
- **Per-mailbox caps** - cap daily sends per mailbox, not just per domain
- **Parallel track** - new domains warm in the background while existing domains carry volume

**Gate:** Runbook with per-domain ramp schedules, caps, and stop conditions.

### Step 5: Scaling Safely
- **Volume ladder** - increase only when quality holds (heuristics - bounce rate under about 2%, complaint rate under about 0.1%; adjust to provider guidance and your own baselines)
- **Step size** - grow volume in modest weekly increments rather than jumps (heuristic - avoid doubling overnight)
- **New-domain lead time** - warm new domains before hiring or expansion adds send volume
- **Quality-first dials** - if placement slips, cut volume before cutting list quality
- **Capacity planning** - keep one warm spare domain so a reputation event never stops the whole motion

**Gate:** Scaling schedule with quality gates between volume steps and a spare-domain policy.

### Step 6: Blacklist & Reputation Monitoring
- **Watchlists** - check major blacklists (Spamhaus, Barracuda, SpamCop) on schedule, plus ESP-side reputation dashboards
- **Alert thresholds** - placement below target, complaint spikes, and blacklist hits trigger the degradation rules
- **Delisting process** - identify cause → fix (prune list, pause domain, find compromised account) → request delisting per the list operator's process
- **Incident log** - record every reputation event with cause and remediation for pattern analysis

**Gate:** Monitoring loop with thresholds, delisting runbook, and an incident log started.

## Practitioner Grounding & Decision Rules

Built from Al Iverson (Spam Resource/Valimail), Laura Atkins (Word to the Wise), Alex Berman, Gmail/Yahoo bulk-sender rules (Feb 2024), plus the email-deliverability and outbound syntheses. Full research: practitioner-intelligence/syntheses/channels-longtail.md.

- **Auth is identity, not delivery** (Iverson — FACT, T1): SPF/DKIM/DMARC passing does not guarantee inbox; reputation comes from recipient behavior (engagement, complaints, bounces).
- **Consistent volume is the reputation governor** (Berman + Gmail docs — EMPIRICAL, T1): 15-30 sends/mailbox/day, never Monday bursts, no sudden doubling; increase slowly and consistently.
- **Per-domain and per-mailbox caps, not just totals** (Berman — EMPIRICAL, T1): multiple mailboxes share a domain's reputation; one mailbox's spike damages all.
- **Recipient-first recovery** (Atkins — PRINCIPLE, T1): a domain dip means cut volume and fix list quality — rotating domains to escape complaints fails.
- **Warm-up automation is a risk, not a guarantee** (Atkins — HYPOTHESIS, T3): mailbox providers may treat automated warm-up tools as negative trust signals; design for recipient-first sending regardless.
- **Seed-tool limits** (Atkins — EMPIRICAL, T1): placement tools are regression detectors, not truth — trust real engagement metrics.

Decision rules:
1. IF scaling volume THEN step weekly with quality gates — bounce <~2%, complaints <0.1%; never double overnight (Berman + Gmail docs — EMPIRICAL, T1).
2. IF volume exceeds ~30/mailbox/day or >2 follow-ups within a week THEN throttle — volume spikes and over-follow-up train spam filters (Berman — EMPIRICAL, T1).
3. IF a domain's placement slips THEN reduced volume → rest → retire, in that order; fix list quality, don't just switch domains (Atkins/Berman — EMPIRICAL, T1).
4. IF a blacklist hit occurs THEN identify cause → fix (prune list, pause domain, find compromised account) → delist per operator process; log the incident (synthesis — HEURISTIC, T2).
5. IF considering automated warm-up tooling THEN treat it as potentially reputation-negative long-term; warm with real engaged recipients where possible (Atkins — HYPOTHESIS, T3).
6. IF a reputation event threatens to halt outbound THEN fail over to a warm spare domain — keep one spare at all times (synthesis — HEURISTIC, T2).
7. IF seed-tool results conflict with real engagement data THEN trust real engagement (opens/clicks/complaints) (Atkins — EMPIRICAL, T1).

## Metrics

- **Per-domain placement trend** — weekly checkpoint; placement below target triggers degradation rules (synthesis — HEURISTIC, T2).
- **Complaint rate** — <0.3% Gmail threshold; escalate at <0.1% target for outbound (Gmail docs + synthesis — FACT/HEURISTIC, T1).
- **Bounce rate** — <~2% target for outbound lists; >5% yellow, >10% red flag at ESPs (synthesis/provider intel — EMPIRICAL, T2/T3).
- **Daily per-mailbox send count** — enforced cap, not advisory (Berman — EMPIRICAL, T1).
- Guardrail: incident log with cause + remediation for pattern analysis.
- Re-measure: daily volume compliance; weekly placement; monthly scaling review.

## Practitioner-Sourced Failure Modes

- Cold email from the primary domain — one complaint spike breaks login and transactional mail (synthesis — HEURISTIC, T2).
- Scaling volume before warmup completes; Monday bursts (Berman — EMPIRICAL, T1).
- Deceptive secondary domains — quick blacklist + legal exposure (synthesis — HEURISTIC, T2).
- Rotating domains to escape complaints instead of fixing list quality (Atkins — EMPIRICAL, T1).
- Ignoring per-mailbox caps while watching only the domain total (Berman — EMPIRICAL, T1).
- No spare capacity — reputation events halt outbound entirely (synthesis — HEURISTIC, T2).

## Sources

1. Al Iverson, Spam Resource (auth-is-not-delivery, reputation mechanics) | spamresource.com | tier 1 | 2026-08-15
2. Laura Atkins, Word to the Wise (recipient-first, warm-up risk, seed-tool limits) | wordtothewise.com + Stripo interview | tier 1 | 2026-08-15
3. Alex Berman, volume caps + deliverability discipline | alexberman.com | tier 1 | 2026-08-15
4. Gmail/Yahoo bulk-sender requirements (Feb 2024) | support.google.com/mail/answer/81126 | tier 1 (FACT) | 2026-08-15
5. Synthesis: practitioner-intelligence/syntheses/email.md, outbound.md, channels-longtail.md | tier 1 | 2026-08-15

## Evaluation & QA

### Domain Ops Rubric
| Criteria | Weak | OK | Strong |
|----------|------|----|--------|
| Separation | Cold email on primary domain | One secondary domain | Purpose-split secondary domains |
| Warmup | None | Per-domain ramp | Parallel warmup + spare domain |
| Rotation | None | Ad-hoc | Policy with health thresholds |
| Monitoring | Manual checks | Scheduled checks | Alerts + incident log |
| Scaling | Volume jumps | Gradual steps | Quality gates between steps |

### Common Failure Modes
- Sending cold email from the primary domain - one complaint spike breaks login and transactional mail
- Scaling volume before warmup completes
- Using a deceptive domain (impersonating another brand) - quick blacklist + legal exposure
- No spare capacity - reputation events halt outbound entirely
- Rotating domains to escape complaints instead of fixing list quality
- Ignoring per-mailbox caps while watching only the domain total
