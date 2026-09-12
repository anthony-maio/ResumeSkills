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

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

## The Bullet Point Problem

Most resumes have weak bullets that list job duties instead of achievements:

❌ **Weak (vague verbs, duty language, no outcome):**
- "Responsible for managing team"
- "Helped with customer service"
- "Worked on improving processes"
- "Assisted with projects"

✅ **Strong (specific verb + concrete object + outcome):**

*Fictional example for structure only — never copy its facts into user output.*
- "Led cross-functional team of [N] to deliver [$ USER-CONFIRMED METRIC] product, increasing revenue by [X]%"
- "Streamlined approval process, reducing cycle time by [X]% (from [baseline] to [new])"

**Anti-fabrication rule:** never invent a metric the user hasn't provided or confirmed — ask first. For numeric estimates, defer to resume-quantifier's ask-first rules.

## Core Frameworks

### 1. The X-Y-Z Formula (Google Method)

**Structure:** "Accomplished [X] as measured by [Y] by doing [Z]"

```
❌ BEFORE: "Managed the deployment pipeline"
✅ AFTER: "Cut deploy time [X]% ([baseline] to [new]) by migrating the pipeline
to GitHub Actions with parallelized test shards"

X = the accomplishment (cut deploy time)
Y = the measured result ([baseline] to [new])
Z = the method (GitHub Actions migration + parallel test shards)
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
"Owned the design-review process for the org, introducing explicit review
bar and RFC acceptance criteria that cut review turnaround from 2 weeks
to 3 days"
```

```
"Drove the org-wide migration from a shared monolith to team-owned
services across [N] teams, unlocking independent deploys and cutting
cross-team incident escalations by [X]%"
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
- "Owned the design review process org-wide (org size if the user confirms it)" — the scope *is* the signal
- Forcing a count onto it ("Attended 30 design reviews") produces a fake-feeling metric that downgrades the claim

Rules:
- A real number exists (user-provided or confirmed) → use it
- No number, but scope is the story → scope-only bullet is fine
- No number and impact is the story → ask the user (see resume-quantifier); never invent
- Before/after pairs are strongest: "from [baseline] to [new] p99", "from 2 weeks to 3 days"

**Length by seniority:** 3–6 bullets for recent roles; 1–2 for roles older than 10 years (resume-formatter owns the canonical bullet-count rule).

## Staff-Level SWE Examples

❌ WEAK (mid-level framing, ticket throughput):
- "Resolved 50+ critical production bugs over 6 months"
- "Collaborated with product team to deliver 12 features"

✅ STRONG (scope → decision → org-level outcome — illustrative structure; magnitudes are placeholders, never copy them):

**Migration leadership:**
- "Drove the migration from a Rails monolith to team-owned services across [N] teams ([N]+ engineers), cutting p99 latency [X]% and ending the shared-release train"

**Technical strategy:**
- "Defined the [N]-year technical strategy for the AI platform adopted by [N] product lines; the serving stack now handles [USER-CONFIRMED METRIC] at [X]% lower cost per 1K inferences"

**Research to production:**
- "Translated published distillation work into a production reranking model, lifting top-3 relevance [X] points while holding p99 serving latency under [threshold]"

**Design-review ownership:**
- "Owned design reviews for the platform org; introduced a lightweight RFC process adopted org-wide, cutting review turnaround from 2 weeks to 3 days"

**Mentorship with outcomes:**
- "Mentored [N] engineers to senior; two now lead their own service areas"

## IC Engineering Examples (keep one per section)

❌ WEAK:
- "Wrote code for new features"
- "Fixed bugs in production"

✅ STRONG:
- "Architected authentication microservice serving [N]+ daily active users, reducing login latency [X]% ([baseline] to [new])"
- "Optimized PostgreSQL queries and added Redis caching, cutting API latency [X]% for [N] DAU"

## Product Management (generic example)

❌ WEAK: "Managed product roadmap"
✅ STRONG: "Defined and executed roadmap for a [$ USER-CONFIRMED METRIC] ARR product, prioritizing [N]+ requests from [N]+ customers into [N] quarterly releases"

Full Sales/Marketing/Customer Success/Data/Ops example sets: see `references/industry-examples.md`.

## Common Mistakes

### Mistake 1: Vague duty language
❌ "Was responsible for customer support"
✅ "Resolved [N]+ tickets daily with [X]% satisfaction" *(only if the user confirms those numbers)*

### Mistake 2: Fake-precision numbers
❌ "Improved performance by 47%" *(invented)*
✅ Ask the user; if truly unknown, write the impact qualitatively or use a marked range they confirm

### Mistake 3: Too vague
❌ "Worked with stakeholders"
✅ "Aligned [N] product teams on the API deprecation schedule, zero breaking changes shipped unannounced"

### Mistake 4: Too long
**Rule: 1–2 lines max.** If over, keep the most impressive single metric and cut the rest.

### Mistake 5: Numbers that read as padding
❌ "Attended 30 design reviews" — activity count that downgrades scope
✅ "Owned the design-review process org-wide"

## Rewriting Process

1. Start with the weak bullet
2. Ask clarifying questions: what did you own? what changed? at what scale? who depended on it?
3. Apply the pattern for the level (X-Y-Z for IC work; scope→decision→outcome for staff work)
4. Only use numbers the user gave you — [USER-CONFIRMED METRIC] for the rest, and ask
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
"Drove the org-wide service migration across [N teams], cutting p99
latency [X]% and ending the shared release train"

### What changed / what we need from you:
- Scale: [N teams — confirm]
- Outcome: [p99 change — confirm or provide actual figure]
- Numbers marked [USER-CONFIRMED METRIC] need your confirmation before submission
```

## Checklist

- ✅ No vague duty verbs ("responsible for", "helped", "worked on")
- ✅ Number present *if* a real one exists; scope-only allowed where quantification would be artificial
- ✅ Every number user-provided or confirmed — [USER-CONFIRMED METRIC] otherwise
- ✅ Specific object and scale (what, how big, who depended on it)
- ✅ 1–2 lines
- ✅ Reads as an achievement owned, not a duty assigned
- ✅ Relevant to the target role
