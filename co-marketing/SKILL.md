---
name: co-marketing
category: partnerships
description: Run joint marketing with partners - webinars, co-authored content, joint launches, audience sharing, campaign mechanics, and attribution between partners.
triggers:
  - "co-marketing"
  - "joint webinar"
  - "co-authored content"
  - "joint launch"
  - "audience sharing"
  - "partner campaign"
  - "joint report"
  - "joint ebook"
inputs:
  - partner_shortlist
  - campaign_goal
  - audience_data
  - content_assets
  - attribution_setup
  - team_bandwidth
outputs:
  - partner_match
  - co_marketing_brief
  - campaign_workback
  - asset_plan
  - shared_attribution_model
  - debrief_report
related_skills:
  - partnership-strategy
  - events-webinars
  - content-calendar
  - product-launch-playbook
  - linkedin-content
  - marketing-messaging/content-strategy
  - marketing-messaging/case-study-builder
  - marketing-optimize/attribution-model-selection
required_context:
  - .context/product-marketing.md
allowed_tools: []
version: 1.0.0
---

## When to Use

Invoke when:
- A partner is ready to do something together and nobody knows what the campaign actually is
- You want joint webinars, co-authored reports, or joint launches instead of logo swaps
- Audience sharing is on the table and data, consent, and attribution rules need defining
- Attribution between two marketing teams is unspoken and will be argued about later
- You want co-marketing to become a repeatable program, not one-off favors

## Workflow

### Step 1: Match the Partner to the Goal
- [ ] Confirm audience overlap: each side names who they want to reach and estimates how many of them live in the other side's audience
- [ ] Check complementarity — products that sit together, not compete; competing pairs create trust problems mid-campaign
- [ ] Align on shared goal and separate goals: each partner states its own success metric and the shared one, in writing
- [ ] Agree size parity expectations up front — a 10x audience imbalance changes what each side should contribute (heuristic - the smaller audience side typically brings more production effort; assumption)
- [ ] Pick partners from a scored shortlist, not whoever asks (see partnership-strategy)

**Gate:** Partner matched with documented overlap, complementarity, and per-side success metrics.

### Step 2: Choose the Format
- [ ] Joint webinar — best for pipeline and expert positioning; needs a strong host pairing and a real takeaway (see events-webinars)
- [ ] Co-authored report or ebook — best for SEO, authority, and lead capture; one side should own the narrative spine to avoid mush
- [ ] Joint launch or bundle — best for activation and cross-sell; requires product and support alignment, not just marketing
- [ ] Community takeover or challenge — best for engagement and audience warmth
- [ ] Match format to goal: awareness goes broad and social, pipeline goes gated and specific
- [ ] Pick one format per campaign — stacked formats dilute execution quality

**Gate:** Single format chosen with a one-paragraph rationale tied to the shared goal.

### Step 3: Define Mechanics and the Workback
- [ ] Write a one-page campaign brief: goal, audience, offer, format, channels, success metric per side
- [ ] Split ownership explicitly: who builds the landing page, who owns the platform, who designs, who promotes when
- [ ] Build the workback from launch date backward — a joint webinar typically needs 4-6 weeks from concept to live (heuristic)
- [ ] Asset checklist: landing page, email copy, social pack, visuals, speaker prep, follow-up sequence
- [ ] Keep one shared living doc as the single source of truth for both teams

**Gate:** Brief written, ownership split documented, workback dated, one shared source of truth.

### Step 4: Plan Audience Sharing and Distribution
- [ ] Define the sharing mechanics: email sends to each other's lists, social amplification schedule, cross-posting rules
- [ ] Agree registration and lead data handling before launch — who gets which leads, under what consent language
- [ ] Respect both brands' cadence rules — don't blast a partner's list twice in a week
- [ ] Write promotion copy variants for each side's tone of voice (see marketing-messaging/brand-voice)
- [ ] Build the follow-up sequence jointly so leads aren't dropped at the handoff

**Gate:** Distribution plan agreed with data-handling rules and joint follow-up built.

### Step 5: Set Attribution Between Partners
- [ ] Agree credit rules before launch: sourced vs influenced, and by which tracking
- [ ] Shared UTM convention: each partner gets its own source value; joint content carries an agreed shared tag (see marketing-optimize/utm-governance)
- [ ] Decide the lead handoff: who contacts which leads, and when — silent duplication kills trust fast
- [ ] Agree the shared dashboard both teams can see; no private spreadsheets
- [ ] Put the attribution agreement in writing even if it feels obvious — it is what gets argued about later

**Gate:** Attribution agreement written, UTM convention live, shared dashboard accessible to both teams.

### Step 6: Debrief and Decide to Repeat
- [ ] Shared post-mortem within a week: results vs each side's metric, what surprised, what broke
- [ ] Publish a short shared results note both teams can circulate internally — it is the currency for the next campaign
- [ ] Decide explicitly: repeat, iterate, or stop — not defaulting to enthusiasm
- [ ] Escalate repeat winners toward a recurring program slot (quarterly webinar, annual report)
- [ ] Bank the assets: recording, report PDF, email copy into the reusable library

**Gate:** Debrief completed with a documented repeat-or-stop decision and assets banked.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Partner match | Chosen by enthusiasm | Overlap checked | Overlap, complementarity, and per-side metrics documented |
| Format | Default webinar | Format picked deliberately | Format tied to goal with single-format discipline |
| Mechanics | Implicit ownership | Ownership split | Brief + dated workback + one source of truth |
| Attribution | Decided after the leads arrive | UTM convention agreed | Written credit rules + shared dashboard + handoff plan |
| Follow-through | Campaign ends | Debrief happens | Repeat-or-stop decision + assets banked |

### Common Failure Modes
- One side does all the promotion while the other harvests the leads
- Attribution decided after launch — the argument is inevitable and unwinnable
- Content about the partners' products instead of the audience's problem
- No consent check on list sharing — a compliance and trust landmine
- Format sprawl — a webinar plus a report plus a challenge means all three under-executed
- Handoff gaps — joint leads that nobody follows up for two weeks
