---
name: resume-bullet-writer
description: Use when rewriting weak resume bullets into achievement statements — verb fixes, honest quantification, and scope framing for IC-through-staff engineering.
---

# Resume Bullet Writer

## When to Use This Skill

Use this skill when the user wants to:
- Write or improve resume bullet points
- Transform weak descriptions into strong achievements
- Add metrics and quantifiable results
- Mentions: "improve my bullets", "make my resume stronger", "quantify my achievements"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Contact info: name, phone, email, city/state, optional links — never street address, DOB, photo. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-looking line, identical everywhere.

**Confidential search (employed users):** Ask before naming the current employer in outreach or public artifacts; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass — prefer percentages, ranges, anonymized phrasing.

## The Bullet Point Problem

Most resumes have weak bullets that list job duties instead of achievements:

❌ **Weak (vague verbs, duty language, no outcome):**
- "Responsible for managing team"
- "Helped with customer service"
- "Worked on improving processes"
- "Assisted with projects"

✅ **Strong (specific verb + concrete object + outcome):**
- "Led cross-functional team of 12 to deliver $2M product, increasing revenue by 35%"
- "Streamlined approval process, reducing cycle time by 40% (from 10 to 6 days)"

**Anti-fabrication rule:** never invent a metric the user hasn't provided or confirmed — ask first. For numeric estimates, defer to resume-quantifier's ask-first rules.

## Core Frameworks

### 1. The X-Y-Z Formula (Google Method)

**Structure:** "Accomplished [X] as measured by [Y] by doing [Z]"

```
❌ BEFORE: "Managed the deployment pipeline"
✅ AFTER: "Cut deploy time 87% (2h to 15min) by migrating the pipeline to
GitHub Actions with parallelized test shards"

X = Cut deploy time 87%
Y = 2h to 15min
Z = GitHub Actions migration + parallel test shards
```

### 2. STAR (condensed for resumes)

Full STAR belongs in interview prep. A resume bullet needs only the condensed **A + R** (action + result):

```
Interview STAR: "Inherited a flaky payments system (S) with 3 weekly
sev-2s. Tasked with stabilizing it (T). Redesigned the retry/idempotency
layer (A). Sev-2s dropped to zero for 6 months (R)."

Resume bullet: "Redesigned retry/idempotency layer for the payments
system, eliminating a 3x/week sev-2 incident pattern for 6+ months"
```

### 3. Staff-level pattern: scope → decision → org-level outcome

At staff level, the strongest bullets often carry *qualitative* scope plus a decision and its org-level consequence:

```
"Owned the design-review process for a 40-engineer org, introducing
loading criteria that cut review turnaround from 2 weeks to 3 days"
```

```
"Drove the org-wide migration from a shared monolith to team-owned
services across 6 teams, unlocking independent deploys and cutting
cross-team incident escalations by half"
```

## On Verbs: What's Actually Wrong

The problem is **not** "managed" — that's an active verb and perfectly fine when the object is specific ("Managed 8-person platform team" ✅). The real problems are:

- **Weak/vague verbs:** "responsible for", "helped", "worked on", "assisted with", "participated in"
- **Duty language:** describes the job, not an outcome ("Responsible for customer support")
- **Missing objects:** "Managed" without saying what or at what scale

Fix the vagueness, not the verb itself. Don't bloat "managed" into "orchestrated" — that reads as padding.

## Curated Verb List (~25, engineering-leadership credible)

Led, Drove, Owned, Built, Designed, Architected, Delivered, Launched, Scaled, Migrated, Reduced, Cut, Eliminated, Improved, Automated, Defined, Set (as in "set technical direction"), Shaped, Partnered, Mentored, Advised, Resolved, Stabilized, Standardized, Negotiated

Every one survives an interview follow-up ("tell me about the time you..."). Avoid gimmick verbs ("clinched", "united", "orchestrated" as a managed-upgrade) and don't inflate — "helped" can honestly become "contributed the X component of...".

## Quantification: Honest, Not Absolutist

**Quantify when a real, defensible number exists. Prefer one honest scale figure (users, QPS, team size, cost) over three activity counts.**

Not every bullet needs a number. Some of the strongest staff-level bullets are qualitative scope statements:
- "Owned the design review process for a 40-engineer org" — no number needed; the scope *is* the signal
- Forcing a count onto it ("Attended 30 design reviews") produces a fake-feeling metric that downgrades the claim

Rules:
- A real number exists (user-provided or confirmed) → use it
- No number, but scope is the story → scope-only bullet is fine
- No number and impact is the story → ask the user (see resume-quantifier); never invent
- Before/after pairs are strongest: "from 500ms to 200ms p99", "from 2 weeks to 3 days"

**Length by seniority:** 3–5 bullets for recent roles; 1–2 for roles older than 10 years.

## Staff-Level SWE Examples

❌ WEAK (mid-level framing, ticket throughput):
- "Resolved 50+ critical production bugs over 6 months"
- "Collaborated with product team to deliver 12 features"

✅ STRONG (scope → decision → org-level outcome):

**Migration leadership:**
- "Drove the migration from a Rails monolith to team-owned services across 6 teams (60+ engineers), cutting p99 latency 40% and ending the shared-release train"

**Technical strategy:**
- "Defined the 2-year technical strategy for the AI platform adopted by 4 product lines; the serving stack now handles 100K requests/min at 38% lower cost per 1K inferences"

**Research to production:**
- "Translated published distillation work into a production reranking model, lifting top-3 relevance 9 points while holding p99 serving latency under 80ms"

**Design-review ownership:**
- "Owned design reviews for the 40-engineer platform org; introduced lightweight RFC process adopted org-wide, cutting review turnaround from 2 weeks to 3 days"

**Mentorship with outcomes:**
- "Mentored 5 engineers to senior; two now lead their own service areas"

## IC Engineering Examples (keep one per section)

❌ WEAK:
- "Wrote code for new features"
- "Fixed bugs in production"

✅ STRONG:
- "Architected authentication microservice serving 500K+ daily active users, reducing login latency 60% (5s to 2s)"
- "Optimized PostgreSQL queries and added Redis caching, cutting API latency 60% for 100K DAU"

## Product Management (generic example)

❌ WEAK: "Managed product roadmap"
✅ STRONG: "Defined and executed roadmap for a $10M ARR product, prioritizing 50+ requests from 200+ customers into 3 quarterly releases"

Full Sales/Marketing/Customer Success/Data/Ops example sets: see `references/industry-examples.md`.

## Common Mistakes

### Mistake 1: Vague duty language
❌ "Was responsible for customer support"
✅ "Resolved 50+ tickets daily with 98% satisfaction" *(only if the user confirms those numbers)*

### Mistake 2: Fake-precision numbers
❌ "Improved performance by 47%" *(invented)*
✅ Ask the user; if truly unknown, write the impact qualitatively or use a marked range they confirm

### Mistake 3: Too vague
❌ "Worked with stakeholders"
✅ "Aligned 4 product teams on the API deprecation schedule, zero breaking changes shipped unannounced"

### Mistake 4: Too long
**Rule: 1–2 lines max.** If over, keep the most impressive single metric and cut the rest.

### Mistake 5: Numbers that read as padding
❌ "Attended 30 design reviews" — activity count that downgrades scope
✅ "Owned the design-review process for a 40-engineer org"

## Rewriting Process

1. Start with the weak bullet
2. Ask clarifying questions: what did you own? what changed? at what scale? who depended on it?
3. Apply the pattern for the level (X-Y-Z for IC work; scope→decision→outcome for staff work)
4. Only use numbers the user gave you — [PLACEHOLDER] for the rest, and ask
5. Trim to 1–2 lines

## Employment Gaps

Present continuous, truthful coverage of the period (consulting, open source, research, caregiving is fine to list plainly) without editorializing. Keep the interview answer consistent with the resume line — same wording, same dates, everywhere.

## Output Format

```markdown
## BULLET IMPROVEMENTS

### Original: "Responsible for the migration project"

### Issues:
- Duty language ("responsible for") with no object or outcome
- No scope or scale
- Reads as assigned work, not owned work

### Improved (staff pattern):
"Drove the org-wide service migration across 6 teams, cutting p99
latency 40% and ending the shared release train"

### What changed / what we need from you:
- Scale: [6 teams — confirm]
- Outcome: [p99 40% — confirm or provide actual figure]
- Numbers marked [PLACEHOLDER] need your confirmation before submission
```

## Checklist

- ✅ No vague duty verbs ("responsible for", "helped", "worked on")
- ✅ Number present *if* a real one exists; scope-only allowed where quantification would be artificial
- ✅ Every number user-provided or confirmed — [PLACEHOLDER] otherwise
- ✅ Specific object and scale (what, how big, who depended on it)
- ✅ 1–2 lines
- ✅ Reads as an achievement owned, not a duty assigned
- ✅ Relevant to the target role
