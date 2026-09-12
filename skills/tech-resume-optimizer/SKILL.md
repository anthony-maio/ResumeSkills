---
name: tech-resume-optimizer
description: Use when optimizing a resume for software/AI engineering roles at senior level or above — skills structure, staff-level scope framing, publications/open-source sections, and technical links.
---

# Tech Resume Optimizer

## When to Use This Skill

Use this skill when the user:
- Is applying for software/AI engineering roles (mid through staff/principal)
- Wants to optimize a technical resume
- Mentions: "tech resume", "software engineer resume", "SWE resume", "staff engineer resume", "ML resume", "AI resume"

Focuses on senior-and-above engineering ICs; for early-career material (bootcamps, GPA, first projects) see `references/early-career.md`.

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Contact info: name, phone, email, city/state, optional links — never street address, DOB, photo. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-looking line, identical everywhere.

**Confidential search (employed users):** Ask before naming the current employer in outreach or public artifacts; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass — prefer percentages, ranges, anonymized phrasing.

## What Tech Screeners Actually Evaluate

1. **Scope of ownership** — systems, teams, blast radius
2. **Scale and impact** — users, traffic, cost, latency, model quality
3. **Technical judgment** — architecture decisions, trade-offs, migrations
4. **Depth where it counts** — can defend every listed technology in interview
5. **Influence** — strategy, design reviews, mentorship, external voice (talks, papers, OSS)

At staff level, hiring committees look for evidence the candidate moved the *org*, not just shipped systems. GitHub activity is not a screening signal at this level.

## The Scope Ladder (diagnose the resume's level)

Read the bullets and place each — and the resume overall — on the ladder:

| Rung | Bullet sounds like | Level signal |
|---|---|---|
| **Features** | "Implemented X", "shipped Y feature" | Junior |
| **Systems** | "Designed/owned service X serving N users" | Mid–senior |
| **Multi-team programs** | "Drove migration across N teams", "owned platform adopted by N product lines" | Senior–staff |
| **Org strategy** | "Defined technical strategy", "set direction for the org's platform", "owned the design-review process" | Staff+ |

**Diagnosis rules:**
- Most bullets on rung 1 → the resume reads junior regardless of title; rewrite to systems-and-up
- All bullets on rung 2 with no cross-team evidence → reads mid-level; surface the multi-team work
- Manager title but staff-IC target → keep technical bullets dominant; frame leadership as technical leadership
- If the honest ceiling is rung 2–3, don't inflate — target roles one rung up

## Tech Resume Structure

```
1. Contact Information (+ links)
2. Professional Summary (recommended for senior+)
3. Technical Skills
4. Experience (technical achievements, scope-first)
5. Publications / Talks / Patents / Open-source
6. Education
7. (Certifications only if genuinely relevant)
```

### Professional Summary (recommended for senior+)

The summary is the primary tailoring surface — never just "optional". Lead with **scope and domain, not tenure**:

❌ "25-year veteran software engineer..." *(leads with age, generic)*
✅ "Staff engineer specializing in LLM inference platforms. Drove the serving-infrastructure migration used by 4 product teams; published applied work on latency-optimized model serving."

### Contact & Links

```
John Developer
San Francisco, CA
john@email.com | (555) 123-4567
linkedin.com/in/johndev · github.com/johndev · johndev.io
```

**Link GitHub only if it shows substantive work** — real projects, meaningful OSS contributions. It is NOT required, and an inactive profile hurts nothing; most staff engineers at major companies have quiet GitHub profiles. For senior+ candidates, publications, patents, and talks are stronger signals and get their own section. Never optimize for a green contribution graph — it's widely known to be gameable and rarely screened.

## Technical Skills Section

```
Languages: Python, TypeScript, Go, SQL
Frameworks: PyTorch, FastAPI, React
Infra: AWS (EC2, Lambda, SageMaker), Docker, Kubernetes, Terraform
AI/ML: LLM serving (vLLM), evaluation harnesses, RAG pipelines
```

- Order by relevance to the target role; categorize rather than one flat list at senior level
- List only what the user can discuss deeply in an interview
- ❌ Skill bars/ratings, Microsoft Office, every technology touched once, outdated tech unless the JD demands it

## Experience Section

**Bullet formula:** [Action verb] + [scope/system] + [scale or org-level outcome] + [technology]

❌ Weak: "Worked on backend services", "Helped improve performance"

✅ Senior IC:
```
• Architected the microservices migration from the monolith, cutting deploy
  time from 2h to 15min and enabling independent team deployments
• Optimized PostgreSQL + Redis caching for a 500K-DAU API, reducing p99
  latency 60% (500ms → 200ms)
```

✅ Staff-level (scope → decision → org-level outcome):
```
• Drove the org-wide migration from a shared monolith to team-owned services
  across 6 teams (60+ engineers), ending the release train and cutting
  cross-team escalations by half
• Defined the 2-year technical strategy for the AI platform adopted by 4
  product lines; the stack now serves 100K req/min at 38% lower cost
• Owned design reviews for the 40-engineer platform org; RFC process cut
  review turnaround from 2 weeks to 3 days
• Mentored 5 engineers to senior; two now lead their own service areas
```

✅ AI/ML flavor:
```
• Took a published distillation technique to production reranking, lifting
  top-3 relevance 9 points while holding p99 serving latency under 80ms
• Built the eval harness (human + automated) now used by 3 model teams as
  the release gate for quality regressions
```

**Metrics that matter at senior+:** users/QPS/data volume served, latency (p50/p99 before→after), cost reduction (%), MTTR/incident reduction, adoption (teams/product lines), model quality (eval lift, win rate), inference cost per 1K requests. Defer numeric sourcing to resume-quantifier's ask-first rules.

## Publications / Talks / Patents / Open-Source

For senior+ candidates this is the highest-leverage section most resumes omit. Citation-style entry plus a one-line applied tie-in to shipped work:

```
PUBLICATIONS & TALKS

• J. Doe, "Latency-Optimized Model Serving for Production LLMs," NeurIPS
  2024 Workshop on Efficient ML. Applied as the serving design behind
  [Company]'s 100K-req/min inference platform.
• "Cutting Inference Cost 10x," KubeCon 2024 talk (2K+ attendees). Methods
  adopted by two internal platform teams.
• Patent US12,345,678 — Adaptive request batching for multi-tenant
  inference. Licensed in the company's managed offering.

OPEN SOURCE

• Maintainer, vLLM (sampling engine; 40+ merged PRs). Contributions
  shipped inside [Company]'s serving stack.
```

Rules:
- Citation format: authors (self bolded), title, venue, year — verbatim, verifiable
- The one-line tie-in ("Applied as...") converts academic credit into engineering-scope evidence
- Open-source entries must show role and substance (maintainer, reviewer, N merged PRs), not just a profile link
- Truthfulness applies fully: list only real papers, patents, and talks the user confirms

## Staff-Level Signals Checklist

A resume reads staff-level when several of these are present and evidenced:
- [ ] **Multi-team scope** — bullets name teams/product lines affected, not just own team
- [ ] **Design-review ownership** — ran or owned the review process/RFC forum
- [ ] **Strategy docs** — authored technical direction adopted beyond own team
- [ ] **Migration leadership** — drove cross-team technical change to completion
- [ ] **Mentorship outcomes** — engineers leveled up, tech leads grown (outcomes, not activity)
- [ ] **Platform adoption** — internal tooling/platform used by N other teams
- [ ] **External voice** — talks, papers, patents, OSS maintainership
- [ ] **Influence without authority** — proposals adopted by teams that didn't report to them

Missing 3+ → the resume undersells; mine the user's history for these before adding more implementation detail.

## Education Section (senior defaults)

```
EDUCATION
B.S. Computer Science | Stanford University
M.S. Machine Learning | Carnegie Mellon
```

Graduation year optional after ~10 years of experience (age proxy — default to omitting); GPA and coursework omitted for senior candidates. Early-career variants (bootcamp, self-taught, certifications-first) live in `references/early-career.md`.

## Dealing with Stack Mismatch

- **Partial match:** lead with what matches; quantify experience with those tools
- **No match:** emphasize adjacent technologies and demonstrated ramp speed — "Extensive Python web framework experience (Django); ramped to FastAPI in production within a quarter"

## Interview Alignment

Only claim technologies the user can discuss deeply; every bullet must have a story behind it (architecture, trade-offs, what broke). A resume line the candidate can't defend is worse than a gap.

## Output Format

```markdown
# TECH RESUME OPTIMIZATION

## Scope-Ladder Diagnosis
- Overall read: [features / systems / multi-team / strategy]
- Highest-rung evidence: [bullet]
- Gaps: [e.g., no multi-team bullet in last 2 roles]

## Skills Restructure
**Current:** [...]
**Optimized:** [categorized, relevance-ordered]

## Experience Improvements
Per bullet: current → improved, with [PLACEHOLDER] for unconfirmed numbers

## Publications / Talks / OSS
- [Section draft from user-confirmed entries, or questions to surface them]

## Staff-Signals Checklist
- [x/8 present; what to mine next]

## Links
- GitHub: include only if substantive; publications line preferred
```
