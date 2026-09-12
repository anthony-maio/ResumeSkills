---
name: offer-comparison-analyzer
description: Use when the user is comparing multiple job offers or weighing an offer against staying put — expected-value equity math, total-comp bands, and weighted decision framework.
---

# Offer Comparison Analyzer

## When to Use This Skill

Use this skill when the user:
- Has multiple job offers to compare
- Is deciding between an offer and staying at their current job
- Needs to evaluate total compensation (including equity done right)
- Mentions: "compare offers", "multiple offers", "which job", "offer comparison", "deciding between jobs"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

## Core Capabilities

- Compare total compensation across offers — with equity valued as expected value, not face value
- Compare offers **against staying put** (mandatory row — see below)
- Create weighted decision frameworks for non-monetary factors
- Identify hidden costs, benefits, and red flags

## Data Sources

- **Posted pay ranges** (pay-transparency postings) are primary, employer-stated data — use them as the anchor for base/band research. See `../salary-negotiation-prep/references/pay-transparency-states.md` for which states require ranges.
- Levels.fyi, Glassdoor, offer letters, recruiter conversations. Crowdsourced self-reports get lower weight than posted ranges and offer documents.

## Equity: Expected Value, Not Face Value

**Do not value equity at grant face value.** All equity math lives in `references/equity-math.md` (single source of truth; `salary-negotiation-prep` points here too). Summary:

- **Private options:** EV = P(success) × (exit common price × diluted shares) − exercise cost − taxes. Account for the 409A-vs-preferred spread (409A is an imperfect proxy for exit proceeds), liquidation preference, and future dilution. Haircuts of 50–90% by stage are **illustrative scenario ranges, not defaults** — the user must supply or confirm every assumption (P(success), exit model, dilution, tax), and the output should show sensitivity to those assumptions.
- **Public RSUs:** liquid and market-linked — value moves with the stock until vest (they are not guaranteed cash), and they are taxed as ordinary income at vest.
- **Private RSUs:** double-trigger = time-based vesting continues per schedule, but settlement (and tax) occurs only at a liquidity event; single-trigger = settlement at vest (tax at vest with no liquidity = cash trap).
- **Always present equity as a Low / Base / High band (±30% around base EV)** with stated assumptions — never a single number.

Flag for the user (don't decide for them): 83(b) 30-day deadline; ISO/AMT trap at exercise.

## Total Compensation Calculator

Components:
- **Cash:** base, signing bonus (year-1 only), target bonus (× target %), commission, relocation
- **Equity:** EV band per above, annualized over the vest schedule
- **Benefits:** 401(k) match, employer health contribution, HSA/FSA
- **Perks:** extra vacation days (× daily base rate), remote savings, development budget

Show every component line so each total visibly sums from the displayed rows. If a user hasn't provided a number, use [PLACEHOLDER] — don't fabricate.

## The Mandatory "Offer vs. Staying Put" Row

Every comparison includes **staying at the current employer** as a real column, not a footnote. For the incumbent column, compute:

1. **Unvested equity vesting over the next 24 months** (shares × current FMV, by vest date) — this is what walking away forfeits
2. **Expected annual refresh grant**
3. **Promotion trajectory** (a promo in flight can change base band and refresh; note level and timing if known)

The forfeited-equity figure also feeds negotiation: it justifies a signing-bonus ask (see `salary-negotiation-prep` → Golden Handcuffs).

*Fictional example for structure only — never copy its facts into user output.*

## Worked Example (all totals sum from displayed rows; every figure annualized where noted)

```
OFFER A — YEAR 1 / ONGOING
Base salary                 $150,000    $150,000
Signing bonus (yr 1 only)    $25,000         —
Target bonus (15%)           $22,500     $22,500
Equity (EV base, band ±30%)  $35,000     $35,000   (low $25K / high $46K)
Benefits (401k + health)     $21,000     $21,000
                          ---------   ---------
YEAR 1 TOTAL               $253,500
ONGOING TOTAL                          $228,500

OFFER B — YEAR 1 / ONGOING
Base salary                 $160,000    $160,000
Signing bonus (yr 1 only)    $10,000         —
Target bonus (10%)           $16,000     $16,000
Equity (EV base, band ±30%)  $60,000     $60,000   (low $42K / high $78K)
Benefits (401k + health)     $24,600     $24,600
                          ---------   ---------
YEAR 1 TOTAL               $270,600
ONGOING TOTAL                          $260,600

STAYING PUT — per year (all rows annualized)
Base salary                 $145,000
Target bonus (12%)           $17,400
Unvested equity (annualized:
  $80K vesting over next
  24 mo ÷ 2)                 $40,000
Expected annual refresh      $30,000
Benefits                     $20,000
                          ---------
ANNUAL TOTAL                $252,400
```

Because equity is a band, report totals as bands too. Offer B ongoing: fixed components ($160K + $16K + $24.6K = $200.6K) + equity band $42K–$78K = **~$242.6K–$278.6K**. If the bands overlap between offers, say the compensation is effectively a tie and decide on the non-monetary factors.

## Side-by-Side Template

```markdown
# OFFER COMPARISON (include "Staying Put" column when employed)

| Component | Offer A | Offer B | Staying Put |
|-----------|---------|---------|-------------|
| Base | $X | $X | $X |
| Signing (yr 1) | $X | $X | — |
| Target bonus | $X | $X | $X |
| Equity (EV band) | $L–$H | $L–$H | $L (unvested vesting/24mo) + refresh |
| Benefits | $X | $X | $X |
| **Year-1 total** | $X | $X | $X |
| **Ongoing total** | $X | $X | $X |
| Equity type / triggers | [RSU dbl-trigger / options…] | | |
```

## Non-Monetary Factors

Score each offer 1–10 per factor, then weight. Typical weights (adjust to the user's stated priorities):

| Factor | Typical weight |
|--------|----------------|
| Total compensation | 25% |
| Career growth | 25% |
| Work-life balance | 20% |
| Team & culture | 20% |
| Location/commute | 10% |

Weighted score = Σ(score × weight) per offer. Use the user's own weights and scores — ask, don't assume.

- **Career growth:** learning, brand, promotion potential, scope, manager quality
- **Work-life:** hours, remote flexibility, vacation culture, on-call, commute
- **Team & culture:** manager (crucial), team health, stability
- **Risk:** funding runway, market position, equity could be worth $0

## Red Flags

**In the offer:**
- ❌ Vague bonus language ("up to 20%")
- ❌ Private equity with no liquidity path or stated preference stack
- ❌ Single-trigger RSUs at a private company (tax at vest, no liquidity)
- ❌ Cliff longer than 1 year
- ❌ **Startup offers only: no vesting acceleration on acquisition** — at a large public company this is standard boilerplate, not a red flag
- ❌ Non-compete restrictions, verbal promises not in writing

**About the company/role:** high turnover, recent layoffs, checked-out manager, funding concerns, responsibilities that keep changing during interviews.

## Decision Tests

- **Gut check:** which offer excites you? which would you regret passing on?
- **Monday morning:** which job do you want to wake up for?
- **Learning:** where do you grow more in 3 years?
- **Risk:** what's the downside of each? which failure would you regret more?

## Output Format

```markdown
# JOB OFFER COMPARISON

## Offers
- **Offer A:** [Role] at [Company] — [Level]
- **Offer B:** [Role] at [Company] — [Level]
- **Staying put:** [Current role] (if employed)

## Total Compensation (bands, not single numbers)
[Side-by-side template above; every total sums from displayed rows]

## Equity Assumptions (per offer)
- [Type; P(success); exit model; preference/dilution; trigger type; tax rate]

## Weighted Non-Monetary Scores
[User's weights and 1–10 scores; weighted totals]

## Key Differences
1. [Difference] 2. [Difference] 3. [Difference]

## Recommendation
Based on stated priorities [X, Y, Z], **[Offer A/B/Staying]** because [reasons tied to the table].

## Clarify Before Deciding
- [ ] [Question per company]
```

## Comparison Checklist

- ✅ Equity valued as EV band (±30%), never face value
- ✅ "Staying put" row included with unvested equity, refresh, promo trajectory
- ✅ Every total sums from displayed rows
- ✅ Posted ranges consumed as primary market data
- ✅ Tax implications flagged (RSU vesting, ISO/AMT, 83(b) deadline)
- ✅ Weighted non-monetary factors using the user's own weights
- ✅ Decision gut-checked against the user's priorities
