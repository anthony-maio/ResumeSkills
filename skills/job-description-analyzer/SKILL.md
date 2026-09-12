---
name: job-description-analyzer
description: Use when analyzing a job posting to decide whether and how to apply — evidence-ranked fit, gap strategy, red flags, and tailoring priorities for senior candidates.
---

# Job Description Analyzer

## When to Use This Skill

Use this skill when the user:
- Wants to analyze a job posting
- Asks "should I apply to this job?"
- Wants to know how well they fit a role
- Needs help understanding job requirements
- Wants to tailor their resume for a specific position
- Mentions: "analyze this job", "am I qualified", "how do I match", "should I apply"

Use this BEFORE resume tailoring to ensure effort is worth it.

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-leaning line, identical everywhere.

**Confidential search (employed users):** Ask before naming the current employer in outreach or public artifacts; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Fabrication guard (gap handling):** Before writing ANY claim about the user's learning activities, certifications, or skills ("I'm learning X", "I hold Y cert", adding a skill to their resume), ask the user what their actual experience with it is. Never insert named courses, self-study claims, or skill-list additions without explicit confirmation. If a gap skill is genuinely absent, write "gap — no evidence; ask the user before addressing it anywhere."

## Analysis Process

### Step 1: Extract Requirements

Break the job description into categories:

**Required (Must-Have)** — education, years of experience, specific technical skills, certifications/licenses, location/work-authorization constraints.

**Preferred (Nice-to-Have)** — "bonus" skills, advanced certifications, domain expertise, specific tool experience.

**Scope & Impact Signals** (most important for senior roles) — system ownership, team/org influence, on-call/incident leadership, technical direction, scale (users, throughput, latency), business metrics.

### Step 2: Evidence-Ranked Fit (replaces any numeric score)

For EACH requirement, rank by evidence from the user's actual resume/statements:

- **Meets** — user has direct, evidenced experience (name the evidence).
- **Partially meets** — adjacent or shallower experience (say how deep it actually goes).
- **Missing** — no evidence. Never paper over this; if a claim would be needed to close it, that's a fabrication risk — ask the user first.

Then give an overall triage — and label it clearly:

> **This triage is a heuristic to prioritize the user's effort. It is not how recruiters or ATS platforms evaluate candidates, and it should not be treated as a probability of success.**

- **Strong fit** — meets nearly all required requirements, with direct evidence for the top 3.
- **Stretch** — meets roughly half; missing items are learnable or compensable by stronger adjacent evidence.
- **Skip** — a hard dealbreaker applies (see below), OR the user confirms the role's core work doesn't interest them.

No overqualified penalty. If the user meets ~100% of requirements and the title is a level down, that is NOT a reason to skip — apply if the scope interests them, and address leveling directly in outreach: "I want this scope, not a bigger title."

### Step 3: Dealbreaker Detection

**Actual dealbreakers (don't apply):**
- Required license/clearance the user can't obtain (medical, legal, CPA, security clearance)
- Location or work-authorization requirement the user can't meet
- Legally mandated qualification (e.g., bar admission for attorney roles)

**NOT dealbreakers (apply anyway):**
- "X+ years" bars — for senior candidates these are wish lists, not hard filters; hiring teams routinely interview people above or below the stated bar. Judge fit by scope evidence.
- "Preferred" degree the user doesn't have
- Nice-to-have tools the user can learn
- Industry experience when the user has transferable skills

### Step 4: Red Flag Detection

**Workload red flags:** "wear many hats", "fast-paced environment", "hit the ground running", "self-starter in ambiguous situations".

**Culture red flags:** "rockstar/ninja/guru", "work hard play hard", "unlimited vacation", "like a family".

**Compensation red flags:** "competitive salary" with no range, equity-heavy comp, commission-based, "DOE" with no range. Note: pay-transparency laws (CO, CA, NY, WA, MA and others) require ranges in many jurisdictions — a missing range where one is legally required is itself a signal.

**AI-washing (flag explicitly):** JDs that say "AI-powered", "LLM experience required", or "GenAI" without describing what the AI actually does or what the person would build. Probe: is this a real ML/LLM engineering role, a conventional role rebranded for funding optics, or prompt-engineering theater? Surface the discrepancy and ask the user how much it matters to them.

## Senior-Engineering Calibration

When the user is a senior/staff engineer:

1. **Weight scope over tool keywords.** "Own the technical direction for payments infrastructure" outranks five framework names. Judge: systems owned, scale (QPS, data volume, uptime), blast radius, org-level influence, incident leadership.
2. **Vague staff+ requirements resist keyword counting** — "set technical vision" is evidenced by narratives (RFCs authored, migrations led, standards set), not resume keywords. Flag these as "evidence-gathering needed: ask the user for 1-2 stories per vague requirement."
3. **Years bars are negotiable.** See dealbreakers above. Don't let a "10+ years" bar cause a strong 22-year candidate to self-select out — or a strong 8-year candidate to skip. The evidence, not the arithmetic, decides.
4. **Prefer referral/warm-intro paths.** Most tech applications get no response regardless of match. Before recommending a cold application, ask: does the user know anyone at the company, or anyone two hops away? A referral or a warm intro to an engineering leader converts far better than a portal submission. Cold-apply as the fallback, not the default.

## Report Skeleton

Output the analysis in this shape (full worked example: `references/example-report.md`):

```markdown
# JOB ANALYSIS: [Role] at [Company]
**Triage:** STRONG FIT / STRETCH / SKIP — *(heuristic; not how recruiters score you)*
**Hard dealbreakers checked:** location / work-auth / license — [result]

## Requirements (evidence-ranked)
| Requirement | Verdict | Evidence |
|---|---|---|
| [Top requirement] | Meets / Partially / Missing | [specific resume evidence or "ask user"] |

## Strengths to emphasize (top 3, with evidence)
## Gaps — and the exact question to ask the user before addressing any of them
## Red flags / AI-washing notes
## Referral & warm-intro check
## Application plan: apply when tailored; one follow-up at 10-14 days
```

Never include fabricated fields: no "estimated competition", no "expected response time", no "posted X days ago → urgency" claims. You don't have that data.

## Application Plan Guidance (candidate-controllable only)

- **Apply when the resume is properly tailored** — not "within 48 hours". Freshness urgency is manufactured; ATS pipelines commonly run 2-4+ weeks.
- **Follow up once**, politely, after **10-14 days** if no response.
- **Contact one relevant person** — the hiring manager or a relevant engineer/EM, with a specific, short note. Not a LinkedIn blast to 2-3 employees.
- **Silence is the default outcome** in the 2026 tech market; it is not evidence the user is unqualified. Prioritize quality over quantity: 10-15 well-targeted applications beat 50 blind ones.

## Company Research Checklist

Before applying, check:
- Glassdoor reviews (patterns in 1-2 star reviews)
- Blind and LinkedIn tenure (high turnover?)
- layoffs.fyi and recent news (layoffs, down-rounds, pivots)
- Levels.fyi and posted ranges (note: many companies under-post or omit ranges even where required)

## Implementation Checklist

1. Extract requirements (required / preferred / scope signals)
2. Rank each requirement by evidence (meets / partially / missing)
3. Assign triage with the heuristic caveat
4. Check hard dealbreakers only
5. List strengths with evidence
6. List gaps with the question to ask the user — never a generated claim
7. Detect red flags and AI-washing
8. Check referral/warm-intro paths
9. Give a candidate-controllable application plan
10. Move on — analysis serves the decision; don't over-polish

## Edge Cases

**Vague job descriptions** — flag as a signal; extract what's possible; suggest asking the recruiter for scope details before investing heavy tailoring.

**Multiple roles in one JD** — identify the core role vs "other duties"; analyze the primary responsibilities; flag scope creep.

**Internal postings** — different strategy: emphasize internal knowledge and cross-team relationships; skip the referral check (you ARE the warm path).

**Reposted jobs** — worth applying, but check whether requirements changed; a repost after a completed search can signal the team doesn't know what it wants.
