---
name: reply-classification
category: outbound
description: Classify outbound replies into positive, negative, objection, and not-interested buckets - routing rules, response playbooks, and a learning loop into sequences.
triggers:
  - "reply classification"
  - "outbound replies"
  - "objection handling"
  - "routing rules"
  - "response playbook"
  - "classify replies"
inputs:
  - reply_archive
  - sequence_map
  - crm_fields
  - handoff_rules
outputs:
  - reply_taxonomy
  - routing_rules
  - response_playbooks
  - learning_log
related_skills:
  - cold-email-sequence
  - multichannel-outbound
  - lead-sourcing-enrichment
  - marketing-messaging/objection-handling
  - marketing-optimize/crm-pipeline-attribution
required_context:
  - .context/product-marketing.md
allowed_tools: []
version: 1.0.0
---

## When to Use

Invoke when:
- Replies pile up unhandled or handled inconsistently
- Reps respond differently to the same objection
- No system for distinguishing real interest from politeness
- Want to automate reply routing
- Sequence copy needs data on why prospects say no

## Workflow

### Step 1: Taxonomy Definition
Build categories that map to actions:

- **Positive** - asks for a meeting, asks about pricing, requests a demo, gives a referral
- **Question** - asks for more information; not committed yet
- **Objection** - specific blocker stated (budget, timing, competitor, authority)
- **Negative/refusal** - explicit no, do not contact
- **Not-interested** - polite brush-off or implicit no without a stated reason
- **System** - out-of-office, auto-reply, vacation responder, address changed
- **Administrative** - unsubscribe, complaint, wrong person, left company

Test the taxonomy against a sample of real replies; adjust until every reply lands in exactly one bucket.

**Gate:** Taxonomy written with definitions, examples, and an "other" escape route reviewed by a human.

### Step 2: Classification Workflow
- **Manual rules** - keyword triggers per category (examples - "calendar", "book time" → positive; "too expensive", "budget" → objection; "not interested", "stop" → not-interested)
- **Automation options** - native CRM sentiment tags, rules engines, or AI classifiers on the reply inbox
- **Confidence tiers** - auto-route high-confidence categories; queue ambiguous ones for human review
- **Handling windows** - positive replies answered same-day; everything else within 24-48 hours (heuristic - reply speed correlates with booked meetings)
- **Feedback loop** - misclassifications get re-labeled and fed back to the classifier

**Gate:** Classification pipeline running with confidence tiers and a misclassification counter.

### Step 3: Routing Rules
- **Positive → AE handoff** - CRM stage change, thread context attached, response SLA in hours; founder/c-suite replies treated as priority
- **Question → SDR answers** - respond from the same thread with the requested info
- **Objection → playbook response + nurture** - SDR replies per playbook; unresolved objections go to nurture with a revisit trigger
- **Negative/not-interested → suppression** - honor immediately, remove from active sequences; add a comeback trigger only if context changes (new funding, job change)
- **System → scheduler** - pause the sequence, reschedule on the return date, skip if permanent
- **Administrative → list hygiene** - unsubscribe and left-company updates flow to suppression (see lead-sourcing-enrichment)

**Gate:** Every category has an owner, an SLA, and the CRM fields it updates.

### Step 4: Response Playbooks per Category
Write the actual replies:

- **Positive** - reply within hours, confirm time via calendar link, prepare the AE with prospect context
- **Question** - answer directly and briefly, end with a next-step ask
- **Objection (top patterns)** - budget (reframe ROI, offer a pilot), timing (respect it, schedule the revisit), competitor (acknowledge, differentiate on one point), authority (offer to loop in the decision maker) - see marketing-messaging/objection-handling for fuller frameworks
- **Negative/refusal** - one gracious close, never argue, leave the door open
- **Not-interested** - polite acknowledgment, remove from sequence, no guilt-trip follow-up

Keep playbooks short enough to use at reply speed; paste-ready where possible.

**Gate:** Playbook for each category with template replies and tone rules.

### Step 5: Learning Loop
- **Objection log** - every objection tagged with a reason code into the CRM
- **Monthly review** - which objections are growing, which sequences produce them
- **Feed the copy** - top objections get addressed preemptively in the next sequence iteration (see cold-email-sequence)
- **Feed the ICP** - high not-interested rates on a segment signal ICP mismatch (see marketing-intelligence/icp-builder)
- **Feed the playbooks** - new objection phrasings update classification keywords and playbook responses

**Gate:** Monthly cadence defined with a report format and owners for each feedback path.

## Practitioner Grounding & Decision Rules

Built from Alex Berman (Experiment 27), Aaron Ross (Predictable Revenue), Steli Efti (Close), Mailshake State of Cold Email 2025, plus the outbound synthesis. Full research: practitioner-intelligence/syntheses/channels-longtail.md.

- **Reply rate is the north metric; classification is where lost value hides** (Ross — HEURISTIC, T1): replies that aren't "book a meeting" (referrals, competitor mentions, "talk to X") are pipeline; unclassified replies are the #1 lost-value trap. Mailshake: 7% of senders don't track replies at all (EMPIRICAL, T1).
- **Positive replies decay fast** (synthesis — HEURISTIC, T1): reply speed correlates with booked meetings; same-day or hours SLA.
- **Yes/no are answers; "maybe" is death** (Efti — HEURISTIC, T1): explicit refusals get a gracious close, never an argument.
- **Never act on 1-2 data points** (synthesis — HEURISTIC, T2): objection/not-interested patterns need n≥10-20 or monthly aggregates before changing sequences or ICP.
- **Objections are copy inputs** (Ross/Berman — HEURISTIC, T1): top objections get addressed preemptively in the next sequence iteration.

Decision rules:
1. IF a reply is positive (meeting, pricing, demo, referral) THEN route to AE same-day with thread context and an hours SLA (synthesis — HEURISTIC, T1).
2. IF a reply is an explicit no THEN suppress immediately and close gracefully — never argue (Efti — HEURISTIC, T1).
3. IF an OOO/auto-reply arrives THEN pause the sequence and reschedule, don't count it as a reply (synthesis — HEURISTIC, T2).
4. IF a referral or competitor mention arrives THEN classify it as value and route it — it is not a lost touch (Ross — HEURISTIC, T1).
5. IF an objection pattern appears in 1-2 replies THEN log it only; change copy/targeting only at monthly aggregate (synthesis — HEURISTIC, T2).
6. IF the same objection appears ≥3x in a month THEN add it to the next sequence iteration preemptively (Ross/Berman — HEURISTIC, T1).
7. IF high not-interested rates cluster on one segment THEN flag ICP mismatch for re-segmentation, not copy rewrite (synthesis — HEURISTIC, T2).

## Metrics

- **Positive reply rate + meetings booked per 1,000 sends** — the pipeline conversion (Mailshake — EMPIRICAL, T1).
- **Reply classification coverage** — % of replies classified; near-total with a human review loop (synthesis — HEURISTIC, T2).
- **Positive SLA adherence** — same-day for positives, ≤24-48h otherwise (synthesis — HEURISTIC, T2).
- **Objection log health** — objections tagged with reason codes, trended monthly, feeding copy (Ross — HEURISTIC, T1).
- Guardrail: misclassification counter feeding the classifier; suppression accuracy (no false positives on "not interested").
- Re-measure: monthly objection review feeding cold-email-sequence and icp-builder.

## Practitioner-Sourced Failure Modes

- Treating every reply as positive and booking junk meetings (synthesis — HEURISTIC, T2).
- Arguing with a refusal — burns the contact forever (Efti — HEURISTIC, T1).
- No SLA on positives — the moment of intent decays fast (synthesis — HEURISTIC, T1).
- Suppressing "not interested" forever with no comeback trigger (synthesis — HEURISTIC, T2).
- Collecting objections but never feeding them into copy and targeting (Ross — EMPIRICAL, T1).
- OOO/auto-replies routed as real replies, breaking the sequence (synthesis — HEURISTIC, T2).

## Sources

1. Alex Berman, outbound discipline essays | alexberman.com | tier 1 | 2026-08-15
2. Aaron Ross, Outbound Validation (reply classification as lost value) | predictablerevenue.com / gtmnow.com | tier 1 | 2026-08-15
3. Steli Efti, reply handling discipline | close.com blog | tier 1 | 2026-08-15
4. Mailshake, State of Cold Email 2025 (reply norms, tracking gaps) | mailshake.com | tier 1 | 2026-08-15
5. Synthesis: practitioner-intelligence/syntheses/outbound.md, channels-longtail.md | tier 1 | 2026-08-15

## Evaluation & QA

### Classification Quality Rubric
| Criteria | Weak | OK | Strong |
|----------|------|----|--------|
| Coverage | Mostly manual | Most replies classified | Near-total with human review loop |
| Positive SLA | Days | Same-day | Hours with AE prepped |
| Suppression | Manual | Rules-based | Automatic + comeback triggers |
| Objection data | Anecdotal | Logged | Tagged, trended, fed to copy |
| Consistency | Rep-dependent | Playbooks exist | Playbooks + monthly review |

### Common Failure Modes
- Treating every reply as positive and booking junk meetings
- Arguing with a refusal instead of closing gracefully (burns the contact forever)
- No SLA on positive replies - the moment of intent decays fast
- Suppressing "not interested" contacts forever with no comeback trigger
- Collecting objections but never feeding them back into copy and targeting
- Auto-replies (OOO) routed as real replies and breaking the sequence
