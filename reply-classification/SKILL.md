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
