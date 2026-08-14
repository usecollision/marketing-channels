---
name: press-pitching
category: pr
description: Build media lists and pitch journalists - angle-matching to beats, pitch email structure, follow-up cadence, and embargo handling.
triggers:
  - "pitch journalists"
  - "media list"
  - "press outreach"
  - "get press coverage"
  - "journalist outreach"
  - "embargo"
inputs:
  - announcement_details
  - target_publication_tiers
  - spokesperson_bio
  - exclusivity_policy
outputs:
  - media_list
  - pitch_emails
  - followup_sequence
  - pitch_tracking_sheet
related_skills:
  - pr-strategy
  - press-release
  - newsjacking
  - podcast-appearances
  - marketing-intelligence/account-intelligence
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- A concrete announcement (launch, funding, data, hire) is ready for outreach
- An existing pitch list is stale or was bought from a database
- Reply rates on pitches are near zero and nobody knows why
- Exclusives or embargoes need to be handled correctly
- Building a long-term media relationship program

## Workflow

### Step 1: Build the Media List
- [ ] For each target publication from pr-strategy, find the right journalists: search past coverage of your category, competitor coverage, and the announcement topic
- [ ] Verify each journalist is active — last article within ~90 days (heuristic; beats change fast)
- [ ] Capture per contact: name, outlet, beat, 2-3 recent articles, email or X handle, notes on style
- [ ] Keep the list focused — 20-40 targets per story is plenty for most teams (heuristic); a huge list usually means weak relevance
- [ ] Tier the list: A (must-land), B (nice-to-land), C (long shot) — pitch A first when exclusivity is on the table

**Gate:** List of 20-40 verified, active journalists with recent-article notes per contact.

### Step 2: Match Angles to Journalists
- [ ] Read the last 3-5 pieces per target — the pitch must reference their actual work
- [ ] Write a one-line "why this journalist" note per contact, tied to a specific angle
- [ ] Build the angle-journalist matrix: angle x journalist with fit scored high/medium/low
- [ ] Assign each A-tier journalist exactly one angle — multiple angles in one email reads as spam
- [ ] Respect beat boundaries: a growth reporter is not a security reporter

**Gate:** Every journalist has one matched angle and a specific reference to their past work.

### Step 3: Write the Pitch
- [ ] Subject line: under ~8 words, concrete, no ALL CAPS (heuristic)
- [ ] First line: reference their specific article or beat — genuine, not flattery
- [ ] Body: one short paragraph — what is new, why their readers care, what you are offering (interview, data, exclusive, access)
- [ ] Offer proof: one stat or link, attributed, not a wall of numbers
- [ ] Close with a clear next step and your contact details
- [ ] No attachments in the first email; no press-kit links unless asked

**Gate:** A pitch under ~150 words that a colleague who knows nothing can read in 30 seconds and summarize.

### Step 4: Send, Follow Up, and Track
- [ ] Send Tuesday-Thursday mornings in the journalist's time zone (convention, not a rule)
- [ ] Follow-up sequence: day +3 short nudge with one new piece of info; day +7 final note offering availability; then stop (heuristic)
- [ ] Never follow up same-day, never guilt-trip ("just bumping"), never re-pitch the same journalist the same angle twice
- [ ] Track every send, reply, and outcome in a sheet: date, journalist, angle, response, next step
- [ ] If a journalist declines, ask (briefly) what would make it a story for them

**Gate:** Every pitch logged with follow-up dates and outcomes; zero follow-ups sent outside the cadence.

### Step 5: Handle Exclusives and Embargoes
- [ ] Exclusives: offer one tier-1 target a real exclusive ("you get this first, on the record") before broad pitch — one outlet only, with a deadline for their decision
- [ ] Embargoes: agree terms in writing before sharing material — what is covered, embargo date/time with time zone, who is bound
- [ ] Never send material to a journalist who did not agree to the embargo
- [ ] If an embargo breaks, contact the outlet immediately; adjust remaining outreach rather than blaming publicly
- [ ] Under-embargo pitches state the date and time in the first line

**Gate:** Every exclusive and embargo has written agreement before material is shared.

### Step 6: Build Long-Term Relationships
- [ ] Send thank-you notes after coverage — short, specific, no asks
- [ ] Share journalists' work when relevant to your audience, without asking for anything
- [ ] Offer yourself as a source on your category even when there is no announcement
- [ ] Keep a running media CRM: beats, preferences (deadlines, email vs X), past stories about you
- [ ] Review the CRM quarterly and prune inactive contacts

**Gate:** Media CRM exists with at least one proactive (non-pitch) touch per key contact per quarter.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| List quality | Bought or guessed contacts | Verified recent activity | Verified + beat-matched + tiered |
| Personalization | "Hi, I love your blog" | References one article | References specific angle fit + their beat |
| Pitch clarity | 3+ paragraphs | One clear paragraph | ~150 words, offer + proof + next step |
| Follow-up | Spammy bumps | Cadence followed | Cadence + new info per touch |
| Tracking | None | Spreadsheet of sends | CRM with outcomes and quarterly review |

### Common Failure Modes
- Mass-pitching 200 contacts with the same email — reply rates collapse and reputation burns
- Referencing an article the journalist didn't write, or misreading their beat
- Following up 6+ times — most practitioners report diminishing returns after 2-3 touches (heuristic)
- Sending embargoed material without prior agreement
- Offering a fake "exclusive" that was already pitched elsewhere
- Treating one no as a dead end instead of asking what would make it a story
