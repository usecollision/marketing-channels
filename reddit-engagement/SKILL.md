---
name: reddit-engagement
category: social
description: Participate in Reddit communities safely - subreddit research, value-first posting, and ban avoidance.
triggers:
  - "Reddit marketing"
  - "Reddit strategy"
  - "subreddit research"
  - "post on Reddit"
  - "Reddit engagement"
  - "avoid Reddit ban"
  - "Reddit AMA"
  - "Reddit communities"
inputs:
  - product_context
  - icp
  - subreddit_list
  - content_assets
outputs:
  - subreddit_fit_matrix
  - rules_compliance_notes
  - value_content_plan
  - posting_schedule
  - engagement_tracker
related_skills:
  - social-strategy
  - community-strategy
  - marketing-intelligence/reddit-research
  - marketing-intelligence/customer-research
  - marketing-intelligence/social-listening
  - marketing-intelligence/review-mining
  - marketing-paid/reddit-ads
required_context:
  - .context/product-marketing.md
allowed_tools:
  - mcp:web-search
version: 1.0.0
---

## When to Use

Invoke when:
- Your ICP hangs out in specific subreddits and you want to participate authentically
- Competitors are mentioned in threads while you're invisible
- Customer questions about your category go unanswered on Reddit
- You want organic Reddit presence instead of (or alongside) Reddit Ads
- A previous attempt got removed or banned and you need a compliant do-over

## Workflow

### Step 1: Subreddit Research & Fit Scoring
- [ ] Find candidate subreddits: topic search, related communities sidebar, competitor/adjacent brand mention tracking
- [ ] Score each: size, activity (posts/day, comment depth), topical relevance to ICP, culture warmth toward vendors
- [ ] Read the top posts of the year per subreddit — this reveals what the community rewards
- [ ] Check mod activity and response patterns; dead mod teams = chaotic norms
- [ ] Shortlist 3-5 communities; depth beats breadth

**Gate:** Fit matrix with scores and evidence; shortlist locked at 3-5 subreddits.

### Step 2: Rules & Culture Immersion (Lurk Phase)
- [ ] Read sidebar, wiki, and pinned posts of every shortlisted subreddit — in full
- [ ] Log self-promotion policy per subreddit (many ban vendor links entirely; others allow flairs or weekly threads)
- [ ] Spend days observing tone: humor, formatting norms, recurring in-jokes, what gets downvoted
- [ ] Note enforcement patterns: what do mods remove, warn, or ban for?
- [ ] Study how accepted vendors participate (if any): the pattern to emulate

**Gate:** Per-subreddit compliance notes written; observation period completed without posting.

### Step 3: Value-First Content Planning
- [ ] Plan content that never mentions your product: tutorials, honest answers, resources, data, AMA expertise
- [ ] Keep self-reference rare (a widely used practitioner heuristic: ~90% value, ~10% brand-mention at most — verify per community norms)
- [ ] Build an answer bank from support tickets and sales questions — real user questions are your best prompts
- [ ] Plan formats that fit each subreddit: in-depth answers, original guides, occasional AMAs or case studies (only where allowed)
- [ ] Pre-draft, then have someone who actually uses Reddit review tone before posting

**Gate:** 2-4 weeks of planned posts/answers per subreddit, all value-first, with disclosure plan where rules require it.

### Step 4: Posting & Engagement Mechanics
- [ ] Account hygiene: real posting history and karma before brand activity — brand-new accounts posting links is a red flag
- [ ] Post in each sub's active hours; timezone patterns matter for early votes (heuristic, validate with your subreddits)
- [ ] Format natively: markdown, flair usage, no emoji-spam, no link-drops in the post body where norms forbid it
- [ ] Engage in comments: be early, be specific, answer follow-ups — the thread is where trust is built
- [ ] When mentioning your brand: full disclosure, minimal pitch, and only where the rules allow

**Gate:** First 10 value posts/answers live with zero removals; comment engagement kept up within 24h.

### Step 5: Ban Avoidance & Reputation Hygiene
- [ ] Red flags to avoid: repeated self-links, identical cross-posts to many subs, voting manipulation, arguing with critics, DM outreach spam
- [ ] Track removal reasons — every removal teaches you the local norm
- [ ] If warned or muted: stop, read rules again, message mods respectfully before posting again
- [ ] Check for shadowbans periodically (log out or use a checker); appeal through proper channels if hit
- [ ] Keep a decision log: what was posted where, when, and how it landed

**Gate:** Zero policy violations across the first month; removal and warning history documented and analyzed.

### Step 6: Measurement & Iteration
- [ ] Track: posts, upvote ratio, comment threads, inbound clicks/mentions, brand sentiment in threads
- [ ] Qualitative wins: "asked on Reddit, bought from us" stories, saved posts, mod invitations
- [ ] Iterate the format mix monthly: what earned the most genuine engagement?
- [ ] Decide the Reddit Ads split: paid amplifies where organic is capped (see marketing-paid/reddit-ads)

**Gate:** Monthly Reddit scorecard with engagement and brand-mention trends; format mix iterated on evidence.

## Evaluation & QA

### Scoring Rubric
| Criteria | Score 1 | Score 3 | Score 5 |
|----------|---------|---------|---------|
| Research | Random subreddits | Fit scores | Evidence-based shortlist with culture notes |
| Compliance | Rules skimmed | Rules logged | Per-sub policy + observation period |
| Value ratio | Brand-first posts | Mixed | Value-first plan with disclosure rules |
| Execution | Sprayed links | Regular posting | Native-format posts + 24h comment SLA |
| Measurement | Nothing tracked | Posts tracked | Engagement + sentiment + iteration |

### Common Failure Modes
- Dropping product links on day one — the fastest path to a ban
- Treating Reddit as a broadcast channel; it's a discussion platform
- Arguing with negative comments instead of listening and learning
- Ignoring subreddit-specific rules while following a "general Reddit" playbook
- Astroturfing or vote manipulation — violates policy and destroys trust permanently
- Undisclosed affiliation — communities punish this harder than the pitch itself
