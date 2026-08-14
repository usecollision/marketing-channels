---
name: product-hunt-launch
category: launch
description: Run a Product Hunt launch - pre-launch checklist, hunter outreach, community prep, launch-day execution, plus Hacker News, BetaList, and directory playbooks.
triggers:
  - "Product Hunt launch"
  - "launch on Product Hunt"
  - "Hacker News launch"
  - "Show HN"
  - "BetaList"
  - "directory listings"
inputs:
  - product_url
  - launch_date
  - community_channels
  - hunter_shortlist
outputs:
  - ph_launch_plan
  - hunter_outreach_messages
  - prep_checklist
  - launch_day_schedule
  - directory_submission_plan
related_skills:
  - product-launch-playbook
  - pr-strategy
  - community-strategy
  - social-strategy
  - reddit-engagement
  - marketing-intelligence/gtm-plan
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Planning a Product Hunt launch for a new or major-updated product
- Preparing a Show HN post on Hacker News
- Submitting to BetaList or planning a directory-listing wave
- Building early adopters and backlinks before the "big" launch
- Note: these are pre-launch and launch-day channels — run them inside product-launch-playbook's timeline

## Workflow

### Step 1: Product Hunt Pre-Launch Checklist
- [ ] Pick the date: Tuesday-Thursday, avoiding major holidays and other big launches (convention)
- [ ] Build the page assets: tagline (one sentence, concrete), 2-5 gallery images or GIFs, demo video, makers list with accurate roles
- [ ] Write the first comment: the story, the problem, what's next — this is read as much as the listing
- [ ] Assemble your supporter list: users, customers, and community members who will genuinely engage
- [ ] Prep distribution: email list segment, Discord or Slack community, X and LinkedIn posts ready to send at launch
- [ ] Read the current PH rules — they change, and rule breaks get launches pulled

**Gate:** Page assets complete, supporter list named, and distribution channels staged.

### Step 2: Hunter Outreach
- [ ] Find active hunters: browse past launches in your category, check who hunted strong recent products, look at leaderboards
- [ ] Approach 2-3 weeks out (heuristic): hunters schedule ahead and care about product quality
- [ ] The ask: short message, what the product is, why their audience fits, launch-date options
- [ ] Give hunters everything: gallery assets, tagline, story, launch-day availability
- [ ] Respect a no — a lukewarm hunter does not help

**Gate:** Hunter confirmed with a date, or a clear fallback plan (maker-launched).

### Step 3: Community Prep
- [ ] Pick 1-2 core communities where you are an actual member — parachuting in on launch day reads as spam
- [ ] Brief ambassadors: what to say, what not to do (no manufactured hype, no vote-begging)
- [ ] Prepare the FAQ: pricing, availability, roadmap questions
- [ ] Never buy votes or coordinate voting — PH enforcement is real and the penalty is launch removal
- [ ] Schedule your own availability: you respond personally all day

**Gate:** Communities briefed with authentic messaging, FAQ ready, and rules compliance confirmed.

### Step 4: Launch Day Execution
- [ ] Post at 00:01 PT (PH convention: launches reset midnight Pacific) — confirm the current convention before launch
- [ ] Drop the first comment immediately after going live
- [ ] Respond to every comment, question, and piece of feedback personally — all day
- [ ] Drive external traffic: email segment, community posts, social — external engagement is legitimate and matters
- [ ] Log metrics hourly: rank, upvotes, comments, signups, referral sources
- [ ] Stay gracious in replies — the audience reads tone as much as product

**Gate:** Live on time, first comment up, every comment answered, traffic sources logging.

### Step 5: Hacker News Playbook
- [ ] Format: Show HN for things people can try now, with a plain technical explanation of what it is and why
- [ ] Post from the founder's account; disclose your role in the first comment — HN punishes astroturfing hard
- [ ] Timing: weekday mornings US time for the biggest audience (heuristic); never coordinate votes
- [ ] Write the title as a factual description, not marketing copy — HN readers downvote hype
- [ ] Expect harsh feedback; treat every objection as data, answer calmly and technically
- [ ] HN is a different audience than PH — optimize the landing page for "what is this, who is it for, how is it built"

**Gate:** Show HN post reviewed against current guidelines, founder-authored, and monitored for comments.

### Step 6: BetaList and Directory Wave
- [ ] BetaList: submit 2-4 weeks before launch (paid review available); it surfaces early adopters pre-PH — use it as a warm-up, not an afterthought
- [ ] Copy variations: write 3 taglines or descriptions and rotate across directories to learn what resonates
- [ ] Directory list: G2, Capterra, SaaSHub, AlternativeTo, indie directories in your category — one wave, not a drip
- [ ] Track every directory with UTM links — most will send little, a few will convert
- [ ] Post-launch: update listings with screenshots, review asks, and new category tags

**Gate:** BetaList live before the main launch, directory submissions tracked with UTMs, top referrers identified.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Prep | Page built on launch morning | Assets staged ahead | Assets + supporters + staged distribution |
| Hunter | None or cold-asked same week | Confirmed | Confirmed with full materials |
| Day-of | Posted, then went quiet | Responded to some comments | Every comment answered personally |
| Rules | Unclear | Read the rules | Rules read + compliance checked with community |
| Follow-through | Metrics never reviewed | Traffic logged | Referrers identified and fed into the next wave |

### Common Failure Modes
- Launching with a rushed page — tagline and gallery are the pitch; weak assets cap the day
- Buying or coordinating votes — the launch gets removed and the community remembers
- Posting and disappearing — unanswered comments are the surest way to kill momentum
- Treating PH rank as the goal — signups and retained users are the goal; rank is a means
- Skipping the first comment — it is where the story actually gets told
- Dumping the same hype post on HN that worked on PH — different audience, different norms
