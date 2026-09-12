---
name: salary-negotiation-prep
description: Use when the user is negotiating a job offer, researching market rates, or preparing counter-offer scripts — includes pay-transparency leverage, salary-history legality, and equity-aware strategy.
---

# Salary Negotiation Prep

## When to Use This Skill

Use this skill when the user wants to:
- Negotiate a job offer or salary
- Research market rates for their role
- Create a counter-offer strategy
- Understand a total compensation package
- Mentions: "salary negotiation", "negotiate offer", "counter offer", "compensation", "how much should I ask for"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

## Core Capabilities

- Research and validate market compensation
- Turn pay-transparency laws into leverage
- Build negotiation strategy and scripts
- Calculate total compensation (not just base)
- Prepare counter-offer responses and pushback plans

## The Negotiation Mindset

1. Negotiation is expected — companies budget for it. A professional, evidence-based counter is usually reasonable but carries some risk; calibrate to your leverage, the employer's urgency, and how much you want the offer.
2. The goal is win-win, not adversarial.
3. Never volunteer your current salary or salary history (see Scenario 5) — anchor to the role's posted/market range instead.

**What you can negotiate:** base salary, signing bonus, annual bonus, equity, level/title, 401(k) match, vacation, remote flexibility, start date, review timing.

## Step 0: Pay Transparency Leverage

**Before any compensation conversation, check the job posting for a legally required pay range.**

- A growing set of states requires posted pay ranges (incl. CA, CO, NY, WA, and MA since Oct 2025); a different, overlapping set bans salary-history questions. Effective dates and employer-size thresholds vary — see `references/pay-transparency-states.md` and **check the specific jurisdiction** before relying on any one state's rule.
- **MA:** range required for employers with 25+ employees effective **Oct 29, 2025** — verify current law before relying on specifics.
- **Remote roles can trigger multiple states' laws at once** — a remote posting reachable from CO, NY, or WA generally must comply with those states' rules regardless of where the company is HQ'd.
- **A missing range where one is required is itself leverage** — ask the recruiter for the posted range for the role.

**How to use a posted range:**
- The posted range is the full band; employers expect to pay near the middle. The posted range is evidence of the employer's stated band, **not a promise that the top is approved for this candidate** — top-of-band typically requires an exceptional case or a higher level.
- **Anchor your counter to the top third of the posted range**, justified by market data and your specifics.
- If the offer is below the posted range, name it: "The posting lists $X–$Y; this offer is below that range."
- If there's no posted range, ask: "Is there a posted or budgeted range for this role?" Many states require one.

## Research Phase

### Step 1: Determine Market Rate

Sources: Levels.fyi (tech), Glassdoor, LinkedIn Salary, Blind, Payscale, Salary.com, public H1B salary data. **Posted ranges from pay-transparency postings are primary data — weight them above crowd-sourced self-reports.** Build a Low (25th) / Target (50th) / High (75th) / Stretch (90th) percentile view of the market.

### Step 2: Know Your Value

Increases worth: rare/specialized skills, track record of results, competing offers, strong referrals, hot market.
May limit: entry level, career change, skill gaps, location arbitrage.

### Step 3: Calculate Total Compensation

Total comp = base + bonus + equity + benefits. Treat equity as a **range** using expected value, never face value — the single source of truth for equity math is `../offer-comparison-analyzer/references/equity-math.md` (EV framework, 409A haircuts, RSU taxation). Do not duplicate that math here; point to it.

## Negotiation Strategy

### When to Negotiate

Best time: after a written offer, before signing.

1. Verbal offer → express enthusiasm, ask for it in writing
2. Written offer → thank them, ask for time to review
3. Research and prepare (24–48 hours)
4. Counter via email or call
5. Discussion (may take rounds) → get final agreement in writing

### Counter-Offer Framework

1. Express enthusiasm
2. Reinforce your value
3. Make a specific ask
4. Justify it (market data, posted range, competing process)
5. Open the discussion

### Counter-Offer Email Template

```
Subject: [Your Name] - Offer Discussion

Hi [Recruiter/Hiring Manager],

Thank you for the offer to join [Company] as [Title]. I'm excited about [specific thing about the role].

After reviewing the details: based on the posted range for this role ($X–$Y) and my [years of experience / specific skill / scope of the role], I was hoping we could discuss a base salary of $[top-third anchor] rather than $[their offer]. I'm flexible and open to talking about the full package — signing bonus and equity included.

Would you have time for a quick call this week?

Best,
[Your Name]
```

### Counter-Offer Call Script

```
"Hi [Name], thanks for making time. I'm really excited about this role — [genuine specific reason].

I've reviewed the offer and want to discuss compensation. The posting listed $X–$Y; based on my [experience/accomplishment], I was hoping for something closer to $[anchor]. Is there flexibility there?"

[LISTEN — let them respond]

[If pushback:] "I understand there are constraints. Could we look at signing bonus, equity, or level to bridge the gap?"

[If they need to check:] "That's fair — when's a good time to reconnect?"
```

### Staff-Level Note: Negotiate the Level, Not Just the Base

At staff+ levels (L6/L7/E6 and equivalents), **the level sets the band** — base, bonus, and equity ranges all hang off it. A $20K base bump is worth far less than coming in one level higher. Ask directly: "What level is this offer calibrated to, and what would it take to come in at [target level]?" Level compounds: refresh grants, promo equity, and every future offer key off it.

### Golden Handcuffs: Price Your Unvested Equity Before Setting a Walk-Away

If the user is currently employed, leaving means forfeiting unvested equity. Before setting any walk-away number:

1. Compute **incumbent unvested equity vesting over the next 24 months** (shares × current price/FMV, by vest date).
2. Add the **expected annual refresh grant** and any promotion in flight (promos usually bump equity, not base).
3. Treat that total as an **opportunity-cost scenario**, not a guaranteed figure: private-company equity should be valued at risk-adjusted expected value (see `../offer-comparison-analyzer/references/equity-math.md`), and even public RSUs carry vest-date price risk. Frame it to the employer accordingly — a **signing bonus is the standard tool to offset forfeited equity**: "I'm walking away from roughly $[X] in unvested equity (risk-adjusted); a signing bonus of $[Y] would offset that."

Never invent share counts or prices — use [PLACEHOLDER] and ask the user for their actual grant data.

## Common Negotiation Scenarios

### Scenario 1: First Offer Is Low

Don't accept immediately; express enthusiasm, then counter with a research- or posted-range-backed number.

```
"I'm thrilled about the opportunity. The base is below what I expected — the posting listed $X–$Y and my research supports that range. Is there room to move closer to $[anchor]?"
```

### Scenario 2: They Ask Your Salary Expectations First

```
"I'm focused on finding the right fit. What's the range you've budgeted for this role?"
```

If pressed: "Based on my research for this role and market, I'm targeting $X–$Y, and I'm open to discussing the full compensation picture." (An *expectation* is fine to state; *history* is not — see Scenario 5.)

### Scenario 3: They Won't Budge on Base

Alternatives: signing bonus (one-time, easiest to approve), additional equity, earlier performance review, extra vacation, remote flexibility, development budget, level/title, relocation, start date.

```
"I understand base is firm. Could we discuss a signing bonus to bridge the gap? Something around $X would make this work — it would also offset equity I'd be forfeiting at my current employer."
```

### Scenario 4: You Have Competing Offers

Only mention if true. **Confirm the offer's existence without volunteering the number** — once you state the other company's figure, the negotiation centers on it, and their number isn't this employer's business.

```
"I want to be transparent — I do have another offer in hand. I'm not going to use their number as a bargaining chip. [Company] is my first choice because [genuine reason], and I want to make sure the package here is competitive for the level. Is there flexibility on [base/equity/signing]?"
```

Never lie about having a competing offer.

### Scenario 5: They Ask Your Current or Past Salary

**Whether asking salary history is legal depends on the jurisdiction — a growing set of states and cities bans the practice.** Check the specific state against `references/pay-transparency-states.md` before characterizing any ask as legal or illegal. Regardless of legality, you never have to volunteer history — do not soften this into a "comply if it's legal" answer, and redirect instead:

**Refusal script (firm, non-deflecting):**
```
"I don't share salary history — let's focus on the range for this role. What's the budgeted range?"
```
Then stop. Don't apologize, don't offer a "ballpark," and don't get drawn into current bonus or unvested equity either — those are history in disguise.

**If pressed:** "Salary history isn't something I provide. My expectations for this role are $X–$Y, and I'm happy to talk about how that fits the band."

**If the ask appears illegal:**
- Note the **date, recruiter name, and company** of the ask, and advise the user to **preserve the record** (screenshot the email/chat, save the voicemail).
- Stay factual: the user may decline to answer, and may report the ask to the state labor agency. Don't threaten litigation on the user's behalf.
- Never assert a specific statute violation beyond what the reference file supports — verify current law for that state first.

## Negotiation Do's and Don'ts

**Do's:**
- ✅ Always negotiate (respectfully)
- ✅ Get the offer in writing before negotiating
- ✅ Check the posting for a legally required range first
- ✅ Be specific with numbers, anchor to the top third of the posted band
- ✅ Express genuine enthusiasm
- ✅ Give them a way to say yes
- ✅ Get the final agreement in writing

**Don'ts:**
- ❌ Accept on the spot
- ❌ Share salary history — banned in a growing set of states and cities (check the jurisdiction), and it only anchors you downward everywhere else; redirect to the role's range
- ❌ Volunteer a competing offer's number (confirm existence only)
- ❌ Make ultimatums or lie about competing offers
- ❌ Accept verbal promises without writing
- ❌ Burn bridges if it doesn't work out

## Comparing Multiple Offers

Side-by-side offer math, expected-value equity treatment, and the mandatory "offer vs. staying put" row live in the **`offer-comparison-analyzer`** skill. Use that skill rather than rebuilding the comparison table here.

## Output Format

```markdown
# SALARY NEGOTIATION STRATEGY

## Pay Transparency Check
**Posted range:** $X–$Y (source: posting; state: [state — verify references/pay-transparency-states.md])
**Anchor:** top third = $X (a stated band, not a promised approval) | **Range missing:** leverage note if required

## Market Research
**Role:** [Title] | **Location:** | **Level:** | **Range:** 25th/50th/75th/90th: $X | **Sources:** [list]

## Their Offer vs. Your Counter
| Component | Offer | Ask | Justification | — rows: Level (sets the band) / Base (top third) / Signing (offsets forfeited equity) / Equity EV range (see equity-math)

## Golden Handcuffs (if employed)
**Unvested vesting next 24 mo:** $[X] | **Expected refresh/promo:** $[X] | **Walk-away:** $[X] — [PLACEHOLDER]s until user supplies grant data

## Counter-Offer Script — [email or call script for this situation]
## If They Push Back — **Plan B:** [elements] | **Walk-away:** [minimum]
## Questions to Clarify — equity (RSU/options, vesting, EV assumptions); bonus (guaranteed vs. target); level
```

## Implementation Checklist

1. ✅ Check the posting for a legally required range (pay transparency)
2. ✅ Research market rate from 3+ sources
3. ✅ Calculate total compensation with equity as an EV range
4. ✅ Price unvested equity if currently employed
5. ✅ Determine walk-away point (including golden handcuffs)
6. ✅ Prepare counter-offer anchored to top third of posted range
7. ✅ Practice the salary-history refusal script
8. ✅ Plan pushback scenarios
9. ✅ Get agreement in writing and review the final letter
