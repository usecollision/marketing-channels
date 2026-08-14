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
