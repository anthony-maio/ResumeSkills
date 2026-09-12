---
name: portfolio-case-study-writer
description: Use when the user is turning resume bullets or project work into detailed portfolio case studies — includes NDA/confidentiality gate, anti-fabrication rules, and staff-SWE/AI-ML worked examples.
---

# Portfolio Case Study Writer

## When to Use This Skill

Use this skill when the user:
- Wants to create portfolio case studies
- Needs to expand resume bullets into detailed writeups
- Is building a portfolio website
- Mentions: "case study", "portfolio", "project writeup", "work samples", "portfolio piece"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation.
**Privacy & age signals:** Never volunteer age proxies (graduation years by default for senior candidates; "20+ years" framing; early-career dates). Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral line used identically everywhere.
**Confidential search (employed users):** Ask before naming the current employer; blind variants. Never publish employer-confidential metrics (revenue, internal infra numbers) without an explicit confidentiality pass — prefer percentages, ranges, anonymized phrasing.

## Anti-Fabrication Rules (non-negotiable)

- **Only real, measured outcomes.** Never invent, round "helpfully," or estimate a metric and present it as measured. If the user didn't measure it, it doesn't go in the case study.
- **If you can't quantify, describe scope instead.** "Owned the migration of 40+ services across 3 teams" is legitimate; "improved efficiency ~35%" (made up) is not.
- **Label percentages correctly — relative vs. absolute.** A drop from 68% to 44% is a **24-percentage-point drop** or a **~35% relative reduction**. "-35%" alone misrepresents it. Always state which you mean.
- **Interview defense test:** every claim must survive **5 minutes of follow-up questioning**. If the user can't explain how a number was measured, what the baseline was, and what confounders existed, cut the number or downgrade it to scope description.

## Step 0: Confidentiality / NDA Gate

**Before writing anything, determine what may be published.** Ask the user:

1. What does their employer/contract permit? (NDA terms, IP assignment, "publicize only with approval" policies, open-source contribution rules)
2. What did they get written approval to share, if anything?

**Anonymization patterns when the employer or details must stay confidential:**
- **Company:** "a Series-B developer-tools company", "a top-5 US e-commerce retailer", "a fintech startup (50 engineers)"
- **Directional metrics:** "reduced p99 latency by roughly a third", "multi-second → sub-second", "single-digit-millisecond" instead of exact figures
- **Percentage-only instead of absolute revenue:** "grew ARR ~40% YoY" without the dollar base
- **NEVER include customer-identifiable data:** customer names, logos, deal sizes tied to a named account, user-level data, screenshots with real names/data
- **Architecture:** describe patterns (event-driven, CQRS, sharded Postgres) without internal service names, infra topology numbers, or security-sensitive details

If the user is unsure what's permitted, default to maximum anonymization and recommend confirming with their manager or legal.

## Case Study Structure

```
1. Overview (project summary + one-line impact)
2. Problem (what needed solving, constraints)
3. Process (research, options considered, decisions + rationale)
4. Solution (what was built; artifacts)
5. Results (measured outcomes, correctly labeled)
6. Learnings (what worked, what you'd change)
```

Target: 3–5 min quick read, 10–15 min deep dive.

**Role-specific emphasis** (full design and PM examples live in `references/design-pm-examples.md`):
- **Product Manager:** strategy, prioritization, stakeholders, metrics, trade-offs
- **UX/Designer:** research, process, artifacts, usability
- **Software Engineer:** architecture, problem-solving, system design, performance
- **Marketing:** strategy, targeting, creative, ROI/attribution

## Worked Example — Staff Software Engineer

```
# Re-Architecting the Real-Time Notification Pipeline

**Company:** a Series-C SaaS company (anonymized per NDA)
**Role:** Staff Software Engineer (tech lead, 6 engineers)
**Timeline:** 2 quarters
**Summary:** Replaced a polling-based notification system with an
event-driven pipeline, cutting p99 delivery latency from 40s to 1.2s
while reducing delivery infrastructure cost per million notifications
by roughly half.

## Problem
- Legacy pipeline polled upstream services every 30s; peak events queued
  for 40+ seconds, causing support spikes during incidents.
- Single consumer scaled vertically; it was the largest single line item
  in the team's infra budget.
- Constraints: zero dropped notifications during migration; no customer-
  facing API changes; 2-quarter deadline.

## Process
- Instrumented the legacy path first: measured per-stage latency and
  drop rate for two weeks to establish a baseline (no baseline, no case
  study numbers).
- Options considered: (a) tune polling interval (rejected: cost scales
  linearly, ceiling ~15s), (b) fan-out consumers on the existing queue
  (rejected: ordering guarantees), (c) event-driven design on a log
  (Kafka-style) with consumer groups (chosen).
- Key decisions: idempotent consumers keyed on notification ID (allows
  at-least-once delivery); per-tenant partitioning for ordering; DLQ
  with replay tooling.

## Solution
- Event producers with schema-versioned envelopes (backward-compatible
  rollout, dual-write during migration)
- Consumer groups with per-tenant rate limiting; shadow deployment
  running both pipelines, diffing outputs for 3 weeks before cutover
- Runbooks + alerting on delivery SLO before cutover

## Results (measured over 60 days post-cutover)
| Metric | Before | After | Change |
|--------|--------|-------|--------|
| p99 delivery latency | 40.1s | 1.2s | ~97% relative reduction |
| p50 delivery latency | 12s | 400ms | ~97% relative reduction |
| Infra cost / 1M notifications | [PLACEHOLDER] | ~50% lower | directional (NDA) |
| Notification loss rate | 0.4% | 0.01% | 0.39 pp drop |

Numbers the user did not measure are shown as [PLACEHOLDER] or
directional — not invented.

## Learnings
- Dual-write + shadow traffic diff caught two ordering bugs the test
  suite missed.
- What I'd do differently: schema registry governance from day one;
  we paid a two-week tax retrofitting it mid-project.
```

## Worked Example — AI/ML Engineer

```
# Shipping an LLM Feature with an Eval Harness and Safe Rollout

**Company:** a Series-B developer-tools company (anonymized)
**Role:** Senior ML Engineer (project lead, 4 engineers + 1 PM)
**Timeline:** 1 quarter to GA
**Summary:** Shipped an AI code-review assistant to [PLACEHOLDER]
active users with a measured acceptance pipeline: offline eval harness,
human-labeled golden set, and staged rollout with automated rollback.

## Problem
- Users wanted automated review comments; the prototype hallucinated
  in demos and leadership wouldn't ship without quality evidence.
- Constraints: p95 review latency budget of 5s; inference cost budget
  per PR; no user data leaves the region (compliance).

## Process — the eval harness came first
- Built a golden set of 500 real (anonymized, user-consented) PRs with
  human labels for "comment worth posting"
- Offline harness scoring: precision@k against golden set, hallucination
  rate (claims about nonexistent code), latency p50/p95, cost per PR
- Model selection: 3 candidates (one fine-tuned small model, two API
  models) evaluated on identical harness runs; the fine-tuned model won
  on cost and latency, lost on precision — chose the mid-size API model
  with a caching layer for the cost/quality trade-off
- Prompt/context decisions: retrieval over the diff + repo tree only
  (not full repo) to hit the latency budget; this cost ~[X] pp precision
  — documented as a known trade-off

## Architecture & latency/cost trade-offs
- Pipeline: diff ingestion → context retrieval → model call → filter
  stage (rules + a small classifier for "postable") → UI
- Caching repeated reviews on identical diffs cut cost per PR by
  [PLACEHOLDER]% (measured in rollout telemetry, not projected)
- Degradation path: if p95 latency exceeds budget, shed to a smaller
  fallback model rather than failing open

## Migration rollout
- 1% of users (internal flag) → 10% → 50% → 100%, gated on eval metrics
  holding; automated rollback if acceptance/precision dropped below
  threshold
- Kill switch per tenant for compliance incidents

## Results
| Metric | Target | Measured at GA |
|--------|--------|----------------|
| Precision@3 vs golden set | ≥80% | [PLACEHOLDER] |
| Hallucination rate | ≤1% | [PLACEHOLDER] |
| p95 latency | ≤5s | [PLACEHOLDER] |
| Cost per reviewed PR | ≤$[X] | [PLACEHOLDER] |

Placeholders stay until the user supplies real measurements.

## Incident writeup
- 3 weeks post-GA, a prompt-version deploy regressed precision silently
  (offline evals passed; live drift). Detection: user "unhelpful" rate
  alert fired within 2h. Response: rolled back the deploy, added a
  live-traffic sampled eval to the harness as a permanent guardrail.
  Writing incidents up like this demonstrates judgment, not just wins.

## Learnings
- Offline evals ≠ live quality; sampled live evals are now standard on
  this team.
- The filter stage was the highest-ROI component — cheap classifier
  gating expensive model output.
```

## Visual Elements

- Must-have: before/after comparisons, architecture diagrams, results charts
- Nice-to-have: journey maps, wireframe evolution, research artifacts
- Blur/redact sensitive data in every screenshot (rerun the NDA gate on images, not just text)

## Output Format

```markdown
# CASE STUDY: [PROJECT NAME]

## Quick Facts
- **Role:** [role] | **Company:** [name or anonymized descriptor]
- **Timeline:** [duration] | **Team:** [composition]
- **Impact:** [one-line result, correctly labeled]

## Overview
[2-3 sentences]

## Problem
[Context, pain points, constraints]

## Process
### Research / baseline
### Options considered
### Key decisions (and why)

## Solution
[What was built; artifacts]

## Results
| Metric | Before | After | Change (label relative vs. absolute) |
[Only measured numbers; scope description otherwise]

## Learnings
[What worked, what you'd do differently]

## Visual Asset List
[Images needed, each NDA-checked]
```

## Quality Checklist

- ✅ Step 0 NDA/confidentiality gate completed; anonymization applied
- ✅ Every metric real, measured, and correctly labeled (relative vs. absolute)
- ✅ No customer-identifiable data anywhere, including screenshots
- ✅ Each claim survives 5 minutes of interview follow-up
- ✅ Scope described where quantification isn't available
- ✅ Your specific contribution is clear (vs. the team's)
- ✅ Honest learnings section
- ✅ Appropriate length (3–10 min read)
