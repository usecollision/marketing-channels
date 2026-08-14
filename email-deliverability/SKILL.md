---
name: email-deliverability
category: email
description: Keep outbound and transactional email out of spam - SPF/DKIM/DMARC authentication, IP and domain warmup, reputation monitoring, and inbox placement testing.
triggers:
  - "email deliverability"
  - "spam folder"
  - "spf dkim dmarc"
  - "domain warmup"
  - "inbox placement"
  - "bounce handling"
  - "sender reputation"
inputs:
  - sending_domain
  - email_platform
  - send_volume_plan
  - bounce_data
outputs:
  - authentication_audit
  - warmup_plan
  - reputation_monitor
  - remediation_playbook
related_skills:
  - cold-email-sequence
  - lifecycle-sequences
  - newsletter-operations
  - domain-reputation-ops
  - marketing-optimize/analytics-setup
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Emails land in spam or promotions despite solid copy
- Setting up a new sending domain or migrating ESPs
- Open/reply rates dropped suddenly
- Expanding send volume (newsletter, outbound, transactional)
- Troubleshooting bounces, blocks, or blacklist notices

## Workflow

### Step 1: Authentication Audit
Verify all three pillars for every sending domain:

**SPF:**
- DNS TXT record lists authorized senders (include your ESP's include mechanism)
- Keep the record under 10 DNS lookups (heuristic - most receivers stop resolving after 10)
- Use -all only after confirming every legitimate sender is covered

**DKIM:**
- Key length 2048-bit (1024-bit is being deprecated by major receivers)
- Selector published and matching the ESP's signing configuration
- Record present on every subdomain used for sending

**DMARC:**
- Policy progression - start p=none, move to quarantine, target reject (heuristic ramp)
- rua reporting address configured and actually monitored
- Alignment mode (relaxed vs strict) matches your sending infrastructure

**Verification:** run `dig txt <domain>` plus third-party checkers (MXToolbox, Google Postmaster Tools) for each record type.

**Gate:** All three records verified on every sending domain with a documented alignment table.

### Step 2: Infrastructure Assessment
Map what sends and how:

- **Dedicated IP vs shared pool** - dedicated IPs need their own warmup and volume; shared pools inherit neighbors' reputation
- **Custom tracking domain** - link clicks routed through your subdomain, not the ESP's shared domain
- **rDNS/PTR record** for any dedicated IP
- **Send source inventory** - transactional, outbound sales, newsletters, and system alerts all affect the same domain reputation
- **Mailbox provider mix** - Gmail/Outlook dominate B2B; measure placement per provider

**Gate:** Infrastructure map shows every sender type, IP assignment, and tracking domain.

### Step 3: Warmup Plan
Warm any new domain or dedicated IP before full volume:

- Ramp volume gradually over 3-6 weeks (heuristic used by major ESPs; adjust to your volume ceiling)
- Start with your most engaged audience (existing customers, recent engagers)
- Keep engagement high early - seed positive signals before cold sends
- Cap daily sends per inbox on shared infrastructure (common heuristic - under 50/day per inbox for new domains)
- Never start warmup with purchased or stale lists

**Gate:** Warmup schedule written with week-by-week volume, audience selection, and stop conditions (bounce spike, complaint spike).

### Step 4: Reputation Monitoring
Set up ongoing measurement:

- **Google Postmaster Tools** - domain/IP reputation, spam rate, authentication status
- **Microsoft SNDS** - IP reputation for Outlook/Hotmail
- **Feedback loops** - register with major ISPs to receive complaint data
- **Seed list testing** - send to inboxes at Gmail/Outlook/Yahoo/Apple to measure placement rate (target high primary-inbox placement - vendor-reported benchmark, verify for your own list)
- **Blacklist checks** - Spamhaus, Barracuda, SpamCop on a fixed schedule

**Gate:** Monitoring stack configured with weekly checkpoint cadence and alert thresholds.

### Step 5: Diagnosis & Remediation
Classify problems before acting:

**Bounce taxonomy:**
- Hard bounces (mailbox does not exist) - suppress permanently
- Soft bounces (temporary - mailbox full, greylisting) - retry up to a cap, then suppress
- Blocks (rejected by the receiving server) - check blacklists and authentication, pause the segment

**Spam-folder diagnosis:**
- Check placement by provider - isolate whether it is global or one mailbox provider
- Review complaint rate - the primary reputation input (vendor guidance - keep spam complaints well under 0.1% of sends)
- Test content triggers - links, images, spam-phrase density
- Isolate content vs infrastructure - same content from a clean domain identifies content issues

**Remediation ladder:** fix authentication → warm reputation → prune unengaged → adjust content → contact postmaster teams at the blocking provider.

**Gate:** Root cause identified with evidence and a sequenced remediation plan.

## Evaluation & QA

### Deliverability Readiness Rubric
| Criteria | Weak | OK | Strong |
|----------|------|----|--------|
| Authentication | SPF only | SPF + DKIM | SPF + DKIM + DMARC with reporting |
| Warmup | None | Ad-hoc ramp | Documented ramp with stop conditions |
| Monitoring | Post-send bounces | Postmaster tools | Postmaster + seed tests + alerts |
| List hygiene | Sends everything | Suppression list | Suppression + engagement-based pruning |
| Bounce handling | Manual | Auto-suppress hard bounces | Classified retries + block pause logic |

### Common Failure Modes
- Sending real volume on a fresh domain without warmup (instant reputation damage)
- No DMARC - others spoofing your domain poisons identity and breaks alignment
- Ignoring complaint rate while chasing send volume
- One shared domain for cold outbound and critical transactional email
- "Fixing" spam placement by resending - doubles complaints
- Assuming the ESP handles everything - authentication and monitoring are sender responsibilities
