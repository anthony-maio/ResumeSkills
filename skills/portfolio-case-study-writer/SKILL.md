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

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

## Anti-Fabrication Rules (non-negotiable)

- **Only real, measured outcomes.** Never invent, round "helpfully," or estimate a metric and present it as measured. If the user didn't measure it, it doesn't go in the case study.
- **If you can't quantify, describe scope instead.** "Owned the migration of 40+ services across 3 teams" is legitimate; "improved efficiency ~35%" (made up) is not.
- **Label percentages correctly — relative vs. absolute.** A drop from 68% to 44% is a **24-percentage-point drop** or a **~35% relative reduction**. "-35%" alone misrepresents it. Always state which you mean.
- **Directional metrics need the same approval as absolute ones.** "Roughly a third," "multi-second → sub-second," "~40% YoY" — each is still a claim about the work; it must trace to something the user measured or confirmed. Get explicit user approval (or an NDA-driven choice) for every directional figure before publishing.
- **Interview defense test:** every claim — measured, directional, or scope — must survive **5 minutes of follow-up questioning** on *provenance* (how was it measured? what was the baseline?) and *permission* (is the user actually allowed to publish this number/diagram/customer story?). If either fails, cut the number or downgrade it to scope description.

## Step 0: Confidentiality / NDA Gate

**Before writing anything, determine what may be published.** Ask the user:

1. What does their employer/contract permit? (NDA terms, IP assignment, "publicize only with approval" policies, open-source contribution rules)
2. What did they get written approval to share, if anything?
3. Is the work itself public? (shipped OSS, launched product, published post-mortem — public work is safer to describe)
4. Who owns the artifacts? (designs, code, docs — portfolio use may need permission even for work the user authored)
5. Do customer-data terms apply? (contractual non-disclosure of customer names/metrics, even "anonymized" ones)
6. Are screenshots/diagrams approved for publication, or text-only? (rerun this gate per artifact)
7. Do post-employment publication rights survive? (some contracts restrict writing about the employer's business after leaving)

**Anonymization patterns when the employer or details must stay confidential:**
- **Company:** "a Series-B developer-tools company", "a top-5 US e-commerce retailer", "a fintech startup (50 engineers)"
- **Directional metrics:** "reduced p99 latency by roughly a third", "multi-second → sub-second", "single-digit-millisecond" instead of exact figures
- **Percentage-only instead of absolute revenue:** "grew ARR ~40% YoY" without the dollar base
- **NEVER include customer-identifiable data:** customer names, logos, deal sizes tied to a named account, user-level data, screenshots with real names/data
- **Architecture:** describe patterns (event-driven, CQRS, sharded Postgres) without internal service names, infra topology numbers, or security-sensitive details

If the user is unsure what's permitted, default to maximum anonymization and recommend confirming with their manager or legal.

## Estimate Policy

Measured outcomes are presented as measured. Estimates or projections appear only in a clearly labeled **estimate/projection subsection**, marked (~ or range) with the derivation — never blended into the Results table as if measured.

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

*Fictional example for structure only — never copy its facts into user output. Bracketed items are placeholders; a real case study carries the user's confirmed numbers.*

```
# Re-Architecting the Real-Time Notification Pipeline

**Company:** a [Company stage] company (anonymized per NDA)
**Role:** Staff Software Engineer (tech lead, [N engineers])
**Timeline:** [duration]
**Summary:** Replaced a polling-based notification system with an
event-driven pipeline, cutting p99 delivery latency from [before] to
[after] while reducing delivery infrastructure cost per million
notifications by roughly half.

## Problem
- Legacy pipeline polled upstream services on a fixed interval; peak
  events queued for [duration], causing support spikes during incidents.
- Single consumer scaled vertically; it was the largest single line item
  in the team's infra budget.
- Constraints: zero dropped notifications during migration; no customer-
  facing API changes; [duration] deadline.

## Process
- Instrumented the legacy path first: measured per-stage latency and
  drop rate for two weeks to establish a baseline (no baseline, no case
  study numbers).
- Options considered: (a) tune polling interval (rejected: cost scales
  linearly, ceiling far above target), (b) fan-out consumers on the
  existing queue (rejected: ordering guarantees), (c) event-driven design
  on a log (Kafka-style) with consumer groups (chosen).
- Key decisions: idempotent consumers keyed on notification ID (allows
  at-least-once delivery); per-tenant partitioning for ordering; DLQ
  with replay tooling.

## Solution
- Event producers with schema-versioned envelopes (backward-compatible rollout, dual-write during migration)
- Consumer groups with per-tenant rate limiting; shadow deployment running both pipelines, diffing outputs for [window] before cutover
- Runbooks + alerting on delivery SLO before cutover

## Results (measured over [window] post-cutover)
| Metric | Before | After | Change |
|--------|--------|-------|--------|
| p99 delivery latency | [measured] | [measured] | [relative/absolute, labeled] |
| p50 delivery latency | [measured] | [measured] | [relative/absolute, labeled] |
| Infra cost / 1M notifications | [PLACEHOLDER] | [directional — user-confirmed] | directional (NDA) |
| Notification loss rate | [measured] | [measured] | [pp drop, labeled] |

Numbers the user did not measure stay [PLACEHOLDER] or directional — never invented.

## Learnings
- Dual-write + shadow traffic diff caught ordering bugs the test suite missed.
- What I'd do differently: schema registry governance from day one — retrofitting it mid-project cost weeks.
```

## Worked Example — AI/ML Engineer

*Fictional example for structure only — never copy its facts into user output. Bracketed items are placeholders; a real case study carries the user's confirmed numbers.*

```
# Shipping an LLM Feature with an Eval Harness and Safe Rollout

**Company:** a [Company stage] developer-tools company (anonymized)
**Role:** Senior ML Engineer (project lead, [N engineers + PM])
**Timeline:** [duration] to GA
**Summary:** Shipped an AI code-review assistant to [PLACEHOLDER]
active users with a measured acceptance pipeline: offline eval harness,
human-labeled golden set, and staged rollout with automated rollback.

## Problem
- Users wanted automated review comments; the prototype hallucinated
  in demos and leadership wouldn't ship without quality evidence.
- Constraints: p95 review latency budget of [target]; inference cost
  budget per PR; no user data leaves the region (compliance).

## Process — the eval harness came first
- Built a golden set of [N] real (anonymized, user-consented) PRs with
  human labels for "comment worth posting"
- Offline harness scoring: precision@k against golden set, hallucination
  rate (claims about nonexistent code), latency p50/p95, cost per PR
- Model selection: [N] candidates (one fine-tuned small model, two API
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
- Internal flag → single-digit % of users → majority → 100%, gated on
  eval metrics
  holding; automated rollback if acceptance/precision dropped below
  threshold
- Kill switch per tenant for compliance incidents

## Results
| Metric (target → measured at GA) | [targets stay placeholders until the user supplies real measurements] |
Precision@3 vs golden set · hallucination rate · p95 latency · cost per reviewed PR — each shown as [PLACEHOLDER] until measured.

## Incident writeup
- Weeks post-GA, a prompt-version deploy regressed precision silently
  (offline evals passed; live drift). Detection: user "unhelpful" rate
  alert fired within hours. Response: rolled back the deploy, added a
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
- ✅ Every metric real, measured, and correctly labeled (relative vs. absolute); directional metrics carry the same approval
- ✅ No customer-identifiable data anywhere, including screenshots
- ✅ Each claim survives 5 minutes of interview follow-up — provenance and permission separately
- ✅ Scope described where quantification isn't available
- ✅ Your specific contribution is clear (vs. the team's)
- ✅ Honest learnings section
- ✅ Appropriate length (3–10 min read)
