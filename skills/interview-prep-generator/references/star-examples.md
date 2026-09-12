# STAR Story Examples

Worked examples for interview-prep-generator. In real use, every metric and fact must come from the user's confirmed experience — these are structural models, not content to copy.

## Example 1: Staff Engineering — Migration at Scale (with scale metrics)

**Question:** "Tell me about a time you led a team through a difficult technical project." / system-design-adjacent behavioral rounds.

```
SITUATION: "Our payments ingestion service was a single-region monolith handling
40K requests per second, and regional outages took all four product teams down
with it. We'd hit the ceiling — p99 latency was 850ms and climbing 10% quarter
over quarter."

TASK: "As the staff engineer owning ingestion, I was responsible for getting us
to a region-sharded architecture without a shipping freeze — the product teams
couldn't stop for a big-bang migration."

ACTION: "I wrote the RFC proposing a strangler-fig migration with dual-writes
and a reconciliation job, and drove it through review with the platform team
and two skeptical directors. I sequenced the migration by traffic weight,
started with our lowest-volume shard, and built automated consistency checks
that compared old and new paths before each cutover. When the reconciliation
job surfaced a currency-rounding divergence in week three, I pulled the
cutover back myself rather than ship a subtle billing bug — we fixed the
rounding, re-ran, and continued."

RESULT: "Eighteen months end to end, four shards live, p99 down from 850ms to
120ms, and zero customer-facing incidents during cutover. The dual-write
pattern I documented became the team's default for migrations — two other
teams have used it since."
```

**Time:** ~2 minutes. **Short version:** "I led a no-freeze migration of a 40K req/s ingestion monolith to a sharded architecture — p99 from 850 to 120ms, zero customer-facing incidents, and the migration pattern got adopted by two other teams."

**Why it works at staff level:** scope (4 dependent teams, 18-month arc), technical judgment (the rollback decision), org impact (the pattern adoption), and scale metrics throughout.

## Example 2: Product Management — Turnaround

**Question:** "Tell me about a time you led a team through a difficult project."

```
SITUATION: "At [Company], our main product was losing customers to a competitor
with a better mobile experience — 5% monthly churn against our normal 2%."

TASK: "As the product manager, I owned turning the mobile product around."

ACTION: "I interviewed 30 churned customers to understand why they left, then
prioritized the 5 features that achieved parity. I restructured the roadmap
with engineering, negotiated two contract developers from leadership, ran
weekly sprint reviews, and beta-tested with 50 of our best customers before
full launch."

RESULT: "We shipped in 3 months; churn returned from 5% to 2% within 60 days,
we recovered 35% of churned customers, and mobile NPS went from 32 to 58."
```

## Example 3: Failure Story (real failure, demonstrated learning)

**Question:** "Tell me about a time you failed."

```
SITUATION: "In my first year as a lead, I pushed to ship a feature on schedule
over the objection of my two senior engineers, who wanted two more weeks for
load testing."

TASK: "I owned the launch decision and the outcome."

ACTION: "We shipped on time — and the feature fell over at 3x expected traffic
on day two. I wrote the postmortem myself, put my override decision at the top
of the causal chain, and changed the team's launch gate: load-test sign-off
from a named engineer is now mandatory, and I've since overridden an
engineering objection exactly zero times."

RESULT: "The gate caught two would-be incidents in the following year. The
humbling part: both engineers stayed, and told me later that owning the failure
publicly was why."
```

**Why it works:** real failure (a shipped mistake with a named cost), the learning is behavioral and verifiable, no blame-shifting.

## Story Banking: Building Versions

For each story in the bank:
- **Full version:** 2 minutes ("tell me about a time...")
- **Short version:** 60 seconds (follow-ups)
- **One-liner:** 15 seconds ("give me an example of...")

## Mapping Resume Bullets to Stories

```
RESUME BULLET: "Led migration of payments ingestion to region-sharded
architecture (40K req/s)"

STAR: [Example 1 above]
Use for: leadership, system design follow-ups, incident leadership, influence
without authority (the RFC + skeptical directors), killing your own darlings
(the rollback)
```

Each strong bullet should map to 2-3 competencies. A bank of 8-10 stories covers a full staff loop.
