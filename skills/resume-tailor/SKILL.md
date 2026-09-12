---
name: resume-tailor
description: Use when tailoring an existing resume to a specific job posting or JD — emphasis, bullet order, keyword mirroring, and truthful versioning, not rewriting from scratch.
---

# Resume Tailor

## When to Use This Skill

Use this skill when the user wants to:
- Customize their resume for a specific job posting
- Adjust emphasis to match job requirements
- Create a targeted version of their resume
- Mentions: "tailor resume", "customize resume", "target role", "specific job", "match job description"

Use AFTER job-description-analyzer to know what to emphasize. Use resume-ats-optimizer for parse/match checking; this skill changes content emphasis only.

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

## The Truth vs. Tailoring Line (read before any edit)

**Acceptable tailoring:**
- Reordering true information *within* a role (bullet order)
- Emphasizing relevant experience in the summary
- Using industry-standard terminology and the JD's vocabulary for skills the user truly has
- Adding context to vague statements (with user-confirmed facts)
- Compressing old roles to make room for relevant ones

**Unacceptable (lying):**
- Adding skills the user doesn't have
- Changing numbers or metrics
- Creating fake experiences
- Claiming titles the user didn't hold
- Stating certifications or courses the user hasn't completed

**Never reorder jobs out of reverse-chronological order.** Parsers and recruiters read dates, not visual order; non-chronological ordering looks like concealment and breaks work-history parsing. Relevance is controlled by bullet order, summary, and skills placement — never by job order.

## Tailoring Process

### Step 1: Analyze the Job (use job-description-analyzer first)
- Identify required skills and keywords
- Note the company's priorities
- Understand the role's primary responsibilities

### Step 2: Audit the Resume
For each section, ask:
- Does this support the candidacy for THIS specific role?
- Is there a better way to phrase this for THIS job?
- Should this bullet be higher or lower in the role?

### Step 3: Make Strategic Adjustments

**Professional Summary:** Rewrite to mirror the job's key requirements (truthfully — lead with scope, not tenure).

**Skills Section:** Reorder most-relevant first; surface true skills using the JD's terminology.

**Experience (stays reverse-chronological, always):**
- Reorder *bullets* within each role: lead with what this employer cares about
- Compress or drop the least relevant bullets (never the whole role)
- Fold JD keywords into existing true bullets

**Education:** Highlight relevant coursework/certifications only if true and recent.

## How to Control Emphasis (instead of reordering jobs)

**1. Bullet order within each role.** Applying for a management-leaning role — lead with the team-scope bullet; applying for an IC-leadership role — lead with the architecture-ownership bullet. Same role, same employer, same dates — only the bullet order changes. Use the user's real scope figures; the counts below are placeholders.

**2. Summary content.** The summary is the primary tailoring surface for senior candidates. Two emphases for the same person:

*Fictional example for structure only — never copy its facts into user output.*

```
IC-leadership emphasis:
"Staff engineer specializing in LLM inference platforms. Led the migration
of serving infrastructure used by [N] product teams; published applied work
on latency-optimized model serving."

Management emphasis (same person):
"Engineering leader for the AI platform org ([N] engineers across [N] teams).
Grew the team from [N] to [N] while shipping the model-serving platform to
production."
```

**3. Skills placement.** Put the JD's top 3–5 true skills first in the skills section; the rest follow in normal order.

**4. Compression.** Roles older than ~10–15 years (or clearly irrelevant ones) can shrink to one line: "Earlier: Data Analyst, [Company] (years omitted)". Flag the trade-off to the user; never remove content they want kept.

## Keyword Form for Tech

If the JD says "LLMs" and the resume says "large language models", use both forms once each — once spelled out, once abbreviated — rather than exact-phrase-only matching. Same for "K8s/Kubernetes" and "postgres/PostgreSQL" (and any bilingual variants, e.g. JD and resume in different languages, only when the user's materials are actually bilingual). Each critical term should appear where a reader expects it: once in skills, once inside a concrete achievement. Never repeat a term solely to raise density.

## Tailoring Scenarios

### Scenario 1: Staff IC role, but recent title is "Engineering Manager"
- Keep technical bullets dominant in each role
- Frame leadership as *technical* leadership: design reviews, migrations, mentorship, strategy docs
- Summary: "Staff engineer (most recently EM)..." or lead with scope (e.g., "Led technical direction for the org's AI platform" — with the user's confirmed org scope)
- Do NOT hide the title — reframe the work under it

### Scenario 2: Manager role, but deeply technical
- Lead with team-scope and org-outcome bullets
- Keep 1–2 hard-technical bullets per role to preserve credibility
- Summary mentions span of ownership (teams, systems, budget) before technologies

### Scenario 3: Staff-engineer resume, two emphases (AI vs platform)
- AI emphasis: lead bullets with model quality, eval results, inference cost; mirror the JD's "LLM inference" vocabulary
- Platform emphasis: lead with scale, reliability, migration outcomes; mirror "platform", "infrastructure", "developer productivity" vocabulary
- Swap which papers/talks appear in the Publications line per version

### Scenario 4: Startup target (coming from big companies)
- Highlight cross-functional work, end-to-end ownership, speed
- De-emphasize process maturity and large-team coordination

### Scenario 5: Big-company target (coming from startups)
- Emphasize work that scaled, cross-team collaboration, operational maturity
- Add user-confirmed metrics that show impact at scale — never invent them for the target

## Version Management

- Maintain ONE master resume with every role and bullet — the source of truth
- Targeted versions: name them per resume-formatter's convention: `FirstName_LastName_Resume_[OptionalRole].pdf`
- Track which version went to which company, and **keep a log of what each version claims** — inflated claims in one version are discoverable inconsistencies across applications and interviews
- Save tailoring notes for interview prep

## Quick Tailoring Checklist

1. ✅ Summary mentions the target job's function and leads with scope
2. ✅ Top skills match the JD's top requirements (truthfully)
3. ✅ Recent roles lead with the most relevant material; don't clone the same first bullet across roles
4. ✅ Jobs remain in strict reverse-chronological order
5. ✅ JD keywords appear naturally, both forms where relevant
6. ✅ Roles older than ~15 years considered for compression
7. ✅ All claims are truthful and consistent with other versions
8. ✅ No age proxies added (graduation years, '20+ years')
9. ✅ File named per resume-formatter's convention; version logged

## Output Format

When tailoring a resume, provide:

```markdown
# TAILORED RESUME CHANGES

## Target: [Job Title] at [Company]

### Professional Summary
**Before:** [Original]
**After:** [Tailored — leads with scope, mirrors JD requirements]

### Skills Section
**New order:** [Reordered list]
**Terminology changes:** [e.g., "large language models (LLMs)"]

### Experience Changes
**[Company] — [Title]** (order unchanged)
- Move bullet X to position 1 (why)
- Modify bullet Y: Before → After
- Compress bullet Z to one line (why)

### Truthfulness Check
- Every added keyword backed by: [bullet or user confirmation]
- Numbers changed: none / [list with user confirmation]

### Version Log
- Company, date, file name, summary of claims made
```

## Implementation Notes

- Always start with the job description analyzer
- Never sacrifice truthful claims or chronological order for match
- Keep tailoring changes documented for interview prep
- Defer numeric estimation to resume-quantifier (ask-first rules apply there)
