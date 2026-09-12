# Equity Math — Expected-Value Framework

Single source of truth for equity valuation across the resume-skill set. Other skills (`salary-negotiation-prep`, etc.) point here rather than restating the math.

## Principle: value equity as a range, never a single face-value number

A grant "worth $200K" at face value is not worth $200K. Compute an **expected value (EV)** with a **low/base/high band (±30% around the base case)** and show the range.

## Private-company options

**EV = P(success) × (exit common price × diluted shares) − exercise cost − taxes**

Walk through each term:

1. **Exit common price.** Model exit outcomes (M&A at revenue multiple, IPO valuation) and take the **common-stock price at exit**, not today's valuation.
2. **409A vs. preferred price.** The 409A is an **independent fair-value estimate of common stock**; it is typically below the preferred price because common lacks the preference rights and liquidity investors pay for. A 409A of $2 with a preferred price of $6 means the last round values the company ~3× the 409A. **Why 409A is an imperfect proxy for exit proceeds:** after the preferred stack is paid out, your common shares capture only a fraction of that spread — and startups keep raising rounds, so dilution and preference keep eating the common's share of proceeds.
3. **Liquidation preference.** Investors get their money back (often 1×, sometimes with participating/multiple preferences) **before common sees a cent**. At a $500M exit, $400M of stacked preference leaves $100M for everyone else's common. Downside case: preference swallows the whole exit and options are worth $0 even though "the company sold."
4. **Dilution.** Future rounds dilute your ownership; multiple planned rounds compound. **Do not assume a default** — ask the user for the expected number of rounds and dilution per round. (15–20% per round is a common illustrative scenario, useful only for sensitivity display, never as a silent default.)
5. **Exercise cost.** shares × strike. Buying underwater or illiquid shares costs real cash now for value that may never arrive.
6. **Taxes.** At exit: NSOs → ordinary income on spread at exercise, capital gains treatment depends on timing; ISOs → AMT risk at exercise (below). Combined leakage depends on holding period and bracket — ~35–52% is a common illustrative range, but the user must confirm their rate; never apply a default silently, and show how the EV moves across the plausible tax range.
7. **P(success).** Your honest probability of a liquidity event that clears the preference stack. Base rates for VC-backed startups reaching a good exit are low; 10–50% is an illustrative scenario range for sensitivity, not a default — the user supplies their own estimate (stage, runway, market), and 100% is never the right input.

**Haircuts are illustrative, not defaults.** A 50–90% face-value haircut depending on stage (late-stage/pre-IPO: ~50%; Series A/B: 80–90%) is a common scenario range — use it only to show sensitivity, and only after the user has supplied or confirmed the underlying assumptions (P(success), exit, dilution, tax). If the resulting EV is negative (strike ≥ realistic exit common price), value it at $0.

## Public-company RSUs

- **Liquid and market-linked, but not guaranteed cash:** value moves with the stock until vest, so pre-vest value is an estimate tied to a price that will change. Taxed as ordinary income at vest (~value on vest date flows through payroll); many holders sell at vest to cover the tax.
- Value = shares × current price × (1 − marginal tax rate), discounted by vest-date price risk (±30% band handles this).
- Liquid at vest (can sell immediately) — materially different risk from private equity, but still stock risk until the vest date.

## Private-company RSUs — the double-trigger vs. single-trigger trap

- **Double-trigger**: two conditions must both occur for settlement — the time-based vesting schedule continues as normal, but **settlement (and the tax event) happens only at a liquidity event** (e.g., acquisition or IPO). If the company never exits, shares settle into nothing and no tax is owed. Standard and the safer structure at private companies.
- **Single-trigger**: **settlement occurs at vest** — shares (or their value) are delivered/taxed on the normal vesting schedule even though the company is private and the shares are **un-sellable**. You owe real cash tax on paper income with no liquidity — the classic "cash trap." This has bankrupted employees at late-stage startups. If an offer contains single-trigger RSUs, ask: 409A trajectory, whether the company will allow sell-to-cover on a tender, and whether they'll convert to double-trigger. Factor the tax cash-outflow into the offer comparison.

## 83(b) election — 30-day deadline

For **restricted stock or early-exercised options**, filing an 83(b) within **30 days of grant** (no exceptions, including weekends — miss it and the election is gone forever) taxes you on today's (low) value instead of each vest's then-FMV. Miss it on appreciating stock and you're taxed at vest as income. **Always flag the 83(b) deadline to a user receiving restricted stock or early exercise.**

## ISO / NSO / the AMT trap

- **ISOs** (incentive stock options): no regular income tax at exercise, **but the bargain element (FMV − strike) hits AMT**. Exercising a large ISO grant in one year can generate a six-figure AMT bill on stock you can't sell (private company). Spread exercises across years; model AMT before exercising.
- **NSOs** (non-qualified): ordinary income at exercise on the spread — simpler, more expensive.
- Qualifying-disposition rules (ISO 1-year/2-year holding) further change the math; flag for the user's tax advisor, don't guess.

## Band output convention

Present equity as: **Low / Base / High** where Low = base−30%, High = base+30% of the EV computation, and state the assumptions (P(success), exit value, preference stack, dilution, tax rate) — each one supplied or confirmed by the user, never defaulted. *Illustrative example only (user-supplied assumptions would replace these):*

```
Grant: 40,000 options @ $1.00 strike, 409A $2.00, preferred $5.00
Assume: 30% exit probability, exit common $6.00, 20% future dilution, ~40% tax
Gross at exit: $6.00 × 40,000 × 0.8 = $192,000
Exercise cost: $40,000 | Tax on $152,000 spread @ 40% = $60,800
EV = 0.30 × ($192,000 − $40,000 − $60,800) = 0.30 × $91,200 ≈ $27K
Base EV ≈ $27K → band: $19K (low) … $36K (high)  [vs. $80K "face value" @ 409A]
```
