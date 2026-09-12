---
name: resume-quantifier
description: Use when a resume lacks metrics — discovery questions to find real numbers, confidential-figure sanitization, and explicitly-requested, marked estimation only.
---

# Resume Quantifier

## When to Use This Skill

Use this skill when the user:
- Needs to add metrics and numbers to their resume
- Has bullets without quantifiable results
- Says they "don't have metrics" or "can't measure impact"
- Mentions: "add metrics", "quantify", "add numbers", "measure impact", "no data"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Contact info: name, phone, email, city/state, optional links — never street address, DOB, photo. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-looking line, identical everywhere.

**Confidential search (employed users):** Ask before naming the current employer in outreach or public artifacts; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass — prefer percentages, ranges, anonymized phrasing.

## Confidential Numbers First (the most common trap)

If the user is currently employed, most hard figures (revenue, cost, traffic, model performance) are employer-confidential. **Never publish employer-confidential metrics without an explicit confidentiality pass.**

Sanitization procedure, applied before any number reaches a resume:
1. **Ask:** "Is this figure public or safe to share externally?"
2. If not, offer these forms in order:
   - **Percentage-only:** "cut inference cost 38%" instead of "$4.2M annual spend"
   - **Range:** "supported 40–60 engineers" instead of an exact headcount
   - **Order of magnitude:** "multi-million-request daily traffic" instead of exact QPS
3. Default to percentage-only when in doubt — it carries the achievement without the sensitive baseline
4. Never combine sanitized figures in a way that recomputes the confidential value (a % plus a public baseline can undo the sanitization — check)

## The Core Rule: Ask, Don't Estimate

**The default path is to ASK the user for every number.** Record their answer verbatim. Never pick, round, or "conservatively shade" a number yourself — a number the agent chose is a fabricated number the user must defend in an interview.

**Estimation is allowed ONLY when the user explicitly asks for it** ("just estimate", "I don't remember, put something reasonable"). In that case:
- Mark every estimated figure with `~` or a range in the draft
- Log the derivation in Estimation Notes (one line the user can say out loud)
- The user approves or corrects each one before it's final

There is no "conservative estimation" default. No studies or statistics justify quantification — the honest case: numbers convey scale cheaply and survive recruiter skimming.

**Coverage target:** most bullets, especially recent roles — not all. Scope-only bullets are fine where a number would be artificial ("Owned design reviews for a 40-engineer org").

## Metric Categories

**1. Money** — revenue, cost saved, budget owned (sanitize first — see above)
**2. Time** — hours saved, cycle time, latency, time-to-market
**3. Percentages** — growth, error reduction, efficiency, conversion
**4. Volume/Scale** — users, QPS, team size, customers, data volume
**5. Quality** — satisfaction, accuracy, SLA adherence, uptime
**6. Frequency** — per day/week/month rates, annual totals

## Discovery Questions

**Scale:** How many people/projects/teams? What budget or traffic? How large was the blast radius?
**Impact:** What changed because of your work? What would have happened without it? What got better/faster/cheaper?
**Comparison:** Before vs. after? Vs. the previous system/baseline/team?

**Senior-engineer discovery script:**
- "What did this system do before vs. after your change?"
- "How many teams depended on it?"
- "What did it cost to run? What does it cost now?"
- "Who adopted it, and what did they switch from?"
- "What broke less often / how much faster / how much cheaper?"

For Sales/Marketing/CS/HR discovery lists, see `references/role-metrics.md`.

## Engineering Metrics by Level

### IC-level engineering
- Performance: latency (p50/p99, before→after), throughput, load time
- Reliability: uptime, MTTR, incident count/severity reduction
- Delivery: deploy frequency, cycle time, time-to-ship
- Quality: bug escape rate, test coverage *only if it was a goal*
- Scale served: DAU, requests/sec, data volume

### Staff-level engineering
- **Org scope:** teams/services owned, engineers affected, product lines served
- **Cost at scale:** infra cost reduction (%), efficiency per request/per customer
- **Adoption:** internal platform adoption (N teams migrated, % of org onboarded)
- **Reliability across orgs:** cross-team incident reduction, fleet-wide MTTR
- **Velocity:** org-level deploy frequency, lead-time changes
- **Mentorship outcomes:** engineers leveled up, tech leads grown

### AI/ML engineering
- **Eval benchmarks:** task accuracy/F1/win-rate before→after, human-preference win rates
- **Inference cost:** cost per 1K requests, GPU utilization, tokens-per-dollar
- **Serving latency:** p50/p99 end-to-end, time-to-first-token
- **Quality lift:** user-facing metric attributable to the model (relevance, retention, acceptance rate)
- **Research→production:** model shipped, traffic served, measurable product outcome

## Estimation Techniques (only on explicit request)

- **Range:** "8–12 engineers", "$100K–150K" — marked in draft
- **Minimum bound:** "100+ customers", "at least 15 concurrent projects"
- **Percentage of a known total:** org had 1,000 engineers → owned services for 20% → "services used by ~200 engineers"
- **Time-based derivation:** 5 reviews/week × 50 weeks = "~250 reviews annually" — logged as derived

Every estimated number carries a one-line derivation in Estimation Notes that the user can say out loud in an interview. If they can't defend it, it doesn't ship.

## Common "I Have No Numbers" Situations

**"I was one person on a team"** → quantify your owned component, honestly scoped: "Contributed the retry layer for the system serving 100K users"
**"I don't have access to business metrics"** → quantify inputs and scale you do know; ask what dashboards existed
**"My job didn't produce measurable outcomes"** → measure the work: docs written and their effect, reviews done, onboarding time
**"Results were confidential"** → sanitization procedure above (percentage/range/order-of-magnitude)
**"I was entry-level"** → throughput and accuracy you directly controlled

## Output Format

```markdown
# RESUME QUANTIFICATION

## Analysis
**Bullets without numbers:** X
**Target:** most bullets, recent roles first — scope-only acceptable where honest

## Per-bullet
### Original: "Managed customer accounts"
**Asked:** How many accounts? Revenue? Retention?
**User answers:** [recorded verbatim or "(estimate requested)" + derivation]
**Quantified:** "Managed portfolio of 40 enterprise accounts, 95% retention" *(user-confirmed)*

## Estimation Notes (only if user explicitly requested estimates)
- "~40 accounts": derived from [user's statement]; marked ~ in draft; user approved Y/N

## Confidentiality Pass
- Figures flagged confidential: [list]
- Sanitized to: [percentage / range / order-of-magnitude]

## Open Questions
- [Numbers still needed from the user]
```

## Quality Checklist

- ✅ Every number came from the user or was explicitly requested as an estimate
- ✅ Estimates marked (~ or range) with logged derivations the user can say aloud
- ✅ Confidential figures sanitized (percentage/range/order-of-magnitude)
- ✅ Scale is clear (what the number means)
- ✅ 2–3 numbers max per bullet
- ✅ Not "every bullet" — scope-only where a count would be artificial

## Numbers to Avoid

- ❌ Numbers you (the agent) picked — always
- ❌ Numbers the user can't explain or defend in an interview
- ❌ Numbers that reveal confidential information
- ❌ Numbers without context ("increased 300%" — from what?)
- ❌ Numbers that make the user look bad
