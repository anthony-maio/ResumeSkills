---
name: resume-section-builder
description: Use when the user needs guidance on a specific resume section — summary, skills, experience, education, order — for any career stage including senior/staff ICs
---

# Resume Section Builder

## When to Use This Skill

Use this skill when the user:
- Needs help with specific resume sections
- Wants to optimize a particular part of their resume
- Is unsure what to include in a section
- Mentions: "resume sections", "skills section", "summary section", "experience section", "what to include"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

## Contact Header Rule

The **recommended minimal set**: name, email, phone, city/state, and optional links (LinkedIn, GitHub, portfolio). The user chooses granularity — email-only is a valid choice, and international or remote-first roles may use a region instead of a city/state.

**Never include:** street address, date of birth, photo, marital status, or any other personal identifier. Two separate reasons: (1) norm — street addresses leak unnecessary PII and enable bias, and photos are unusual on US resumes largely for discrimination-risk reasons (they are expected in some other countries); (2) parsing — some ATS handle images poorly, so any photo-based content adds avoidable parsing risk. Keep the norm advice and the parser claims distinct in your reasoning.

## Professional Summary Section

### When to Include

**Include if:** career changer (explain transition), senior/staff professional (distill a long career), returning to workforce, highly specialized role fit.
**Skip if:** entry level with little experience, straightforward progression, space at a premium.

### Summary Framework

**Formula:** [Title/Identity] + [Years — optional] + [Key Skills] + [Value Proposition]

**Years rule:** years of experience are optional in the summary. If included for a senior candidate, cap the framing at "15+" — never "20+" or "25+" — or omit years entirely and let scope carry the seniority ("led platform org of 40 engineers").

### By Career Stage

**Entry Level:**
```
Recent Computer Science graduate from [University] with internship experience in full-stack development. Skilled in Python, React, and AWS. Seeking to apply machine learning and user-facing application projects in a software engineering role.
```

*Fictional example for structure only — never copy its facts into user output.*

**Mid-Career:**
```
Product Manager with 6 years driving B2B SaaS products from concept to scale. Launched products generating [USER-CONFIRMED METRIC] ARR through data-driven roadmap prioritization and cross-functional leadership. Expert in API products and developer tools.
```

**Senior IC (staff/principal engineer, senior PM — technical depth, not headcount):**
```
Staff Software Engineer specializing in distributed systems and platform infrastructure. Led design and delivery of the deployment platform adopted by [USER-CONFIRMED METRIC] engineers; cut p99 checkout latency [USER-CONFIRMED METRIC]% and halved deploy time org-wide. Trusted technical lead for cross-team architecture, design reviews, and incident command.
```

**Senior/Executive (people/organizational leadership):**
```
Technology executive with 15+ years building engineering organizations from 50 to 500+ across global markets. Led platform modernization, M&A integration, and digital transformation with [USER-CONFIRMED METRIC] P&L ownership.
```

**Career Changer:**
```
Sales professional transitioning to Customer Success, bringing 5 years of consultative selling and client-relationship building. Skilled in needs assessment, solution design, and stakeholder management.
```
(All metrics in examples are placeholders — [USER-CONFIRMED METRIC] in the user's real resume.)

### Summary Don'ts
- ❌ "Seeking a challenging position..." / "Hard-working team player..." / "Results-oriented professional..."
- ❌ Third person; objectives (what you want vs. offer)
- ❌ Years framing beyond "15+"

## Skills Section

### Organization Options

**Option 1 — Simple list** (ATS-friendly, space-constrained):
```
SKILLS
Python, JavaScript, SQL, React, Node.js, AWS, Docker, Git
```

**Option 2 — Categorized** (technical roles, extensive sets):
```
TECHNICAL SKILLS
Languages: Python, JavaScript, TypeScript, SQL
Frameworks: React, Node.js, Django, FastAPI
Cloud: AWS (EC2, S3, Lambda), GCP, Docker, Kubernetes
Tools: Git, Datadog, Terraform
```

**Option 3 — Proficiency levels** (only if honest and required by the role).

**Include:** programming languages, tools, methodologies, platforms, certifications, domain knowledge.
**Exclude:** Microsoft Office (assumed), "basic" skills, anything undiscussable in an interview, listed soft skills (show them in Experience), dead technologies.

## Experience Section

### Older Roles — Definition and Handling

**"Older roles" = anything beyond ~10-15 years back.** Compress them to a single line each (or one collective line) — e.g. `EARLIER CAREER — Software Engineer, OldCorp ([YEARS]) · Junior Developer, StartupX ([YEARS])` — no bullets, no detailed dates. Reasons: relevance decay, length control, and age-signal hygiene. Exception: a still-relevant older role can stay detailed when the target posting calls for it.

### Bullet Guidelines by Career Stage

**Entry (0-2 yrs):** 3-5 bullets/role, include relevant projects, quantify where real numbers exist.

**Mid (3-10 yrs):** 4-6 bullets recent roles, 2-3 for older roles (within horizon), achievements over duties.

**Senior IC (10+ yrs, staff/principal):** 5-6 bullets recent roles — emphasize growing scope across several dimensions: systems owned, architecture decisions, adoption of what you built, teams that depend on your platform, and influence on other teams' designs; mentoring too. Audience size (e.g. engineers served) is one useful dimension, not the whole story.

**Senior/Executive (10+ yrs, leadership):** 5-6 bullets recent roles — leadership and strategy, org growth, business impact.

### Standard Format

```
COMPANY NAME | City, State
Job Title | Start Date - End Date

• Achievement bullet with metric and impact
```

### Situations

**Multiple roles, one company:** stack under one company header with per-role dates — shows progression. **Short tenure:** include if relevant, frame around achievement, never explain on the resume. **Contract/freelance:** one heading, client list, strongest achievements.

## Education Section

### Graduation-Year Rule (firm, for industry resumes)
**For industry resumes, senior candidates (10+ yrs) omit graduation years by default** — degree + institution only; the year is an age proxy with zero upside. Entry/mid keep years. **Academic CVs follow field conventions instead** — see `academic-cv-builder` (complete records are expected there).

**Entry/mid:** degree, major, school, year (GPA 3.5+ if strong — entry only; honors and relevant coursework early-career). **Senior:** degree, school — **no year**; executive education may matter more.

```
EDUCATION
B.S. Computer Science
[University]
```

**Certifications** (keep dates — they signal currency): `AWS Solutions Architect Associate | [YEAR] | PMP | [YEAR]`.

## Section Order

### Standard
1. Contact
2. Summary (optional)
3. Skills
4. Experience
5. Education
6. Additional

### Staff/Senior IC Technical
1. Contact
2. Summary
3. Experience (first — the work is the signal)
4. Skills (compact scannable block, not a wall)
5. Projects / Open Source
6. Education — **last, no dates**

### Technical (mid-level)
1. Contact
2. Skills (prioritized)
3. Experience
4. Projects
5. Education
6. Certifications

### Recent Graduate
1. Contact
2. Education (prioritized)
3. Skills
4. Experience/Internships
5. Projects

### Executive
1. Contact
2. Executive Summary
3. Career Highlights
4. Experience
5. Board Roles
6. Education

### Career Changer
1. Contact
2. Summary (explaining transition)
3. Skills (transferable)
4. Experience (reframed)
5. Bridge Experience
6. Education

## Additional Sections

**Projects/OSS:** entry level, career changers, staff+ ICs (proof of craft). **Volunteer:** only when relevant or leadership-signaling. **Languages:** only beyond basic conversational, honest levels. **Publications/Patents:** academic, research, thought leadership. **Awards:** significant industry or company-wide recognition only.

## Output Format

```markdown
# RESUME SECTION RECOMMENDATIONS

## For: [User's situation/role]

### Recommended Section Order
1. [Section] - [Why]

### Section Details

#### Contact Header
[Minimal set confirmation: name/phone/email/city-state/links]

#### Professional Summary
**Recommendation:** [Include/Skip] | **Years:** [shown / 15+ / omitted]
**Draft:** [summary]

#### Skills Section
**Format:** [Simple/Categorized] | **Content:** [organized list]

#### Experience Section
**Horizon:** [which roles detailed vs. Earlier Career line]
**Bullets per role:** [recent: X, older: X]

#### Education Section
**Include:** [items] | **Graduation year:** [include/omit + why]

#### Additional Sections
**Recommended:** [section] because [reason] | **Skip:** [section] because [reason]
```

## Section-Building Checklist

- ✅ Section order optimized for role and level (incl. senior-IC variant)
- ✅ Contact header is the recommended minimal set — no address/DOB/photo
- ✅ Summary years capped at "15+" or omitted
- ✅ Experience bullets achievement-focused with **real** metrics only
- ✅ Roles beyond ~10-15 years compressed to "Earlier Career"
- ✅ Graduation years omitted for senior candidates
- ✅ Total length appropriate (1-2 pages; 2-3 only for executive search)
