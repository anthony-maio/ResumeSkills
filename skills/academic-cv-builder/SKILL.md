---
name: academic-cv-builder
description: Use when the user is applying for faculty, postdoc, or research-academic positions and needs a CV with publications, grants, and teaching. NOT for industry resumes — use tech-resume-optimizer or resume-formatter instead.
---

# Academic CV Builder

## When to Use This Skill

Use this skill **only for research-academic positions**: faculty (tenure-track, lecturer), postdocs, research scientists, and academic administration. Industry and general resumes are handled by other skills — this structure actively hurts outside academia.

Use when the user:
- Is applying for academic positions (faculty, research, postdoc)
- Needs to create or update a curriculum vitae
- Wants to format publications, grants, and teaching experience
- Mentions: "academic CV", "curriculum vitae", "faculty position", "research CV", "professor resume"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

*(Academic privacy note: academic CVs conventionally include degree years and full chronology — the "omit graduation years by default" line above is the US industry-resume norm; academic search committees expect complete records. For confidential applications, follow the user's instruction on what may be named.)*

## Academic CV vs. Resume

| Resume | Academic CV |
|--------|------------|
| 1-2 pages | 2-20+ pages (grows with career) |
| Highlights relevant experience | Comprehensive record |
| Results-focused | Scholarship-focused |
| Skills section prominent | Publications prominent |
| Education minimal | Education detailed |

## Standard Academic CV Sections

```
1. Contact Information
2. Education
3. Research/Academic Positions
4. Publications
5. Presentations
6. Grants & Funding
7. Teaching Experience
8. Mentoring
9. Service
10. Professional Memberships
11. Honors & Awards
12. References (named — see below)
```

**Section order varies by position type:** research positions lead with publications/grants; teaching positions lead with teaching; administrative with leadership/service. Full role-specific emphasis and discipline conventions: `references/discipline-conventions.md`.

## Section-by-Section Guide

### 1. Contact Information

```
FIRST MIDDLE LAST, Ph.D.
Department of [Field], [University]
[City, State ZIP]
Email: [email] | Phone: [phone]
Web: [site] | ORCID: [ORCID]
```

### 2. Education

```
EDUCATION
Ph.D. in [Field], [University], [Year]
  Dissertation: "[Title]"
  Advisor: [Advisor]
  Committee: [Name], [Name], [Name]
M.S. in [Field], [University], [Year]
B.S. in [Field], [University], [Year] ([honors])
```

Include all degrees reverse-chronologically, dissertation title, advisor, committee (PhD), honors, relevant certificates.

### 3. Research/Academic Positions

```
ACADEMIC APPOINTMENTS
Assistant Professor of [Field], [University], [Year]–Present
Postdoctoral Fellow, [University], [Year]–[Year] (Advisor: [Name])
Graduate Research Assistant, [University], [Year]–[Year]
```

### 4. Publications (most important section for research positions)

Numbered list (sciences) or categorized (journal articles / chapters / books / under review / in preparation). Bold your name; include DOIs; mark student co-authors; follow your field's chronological-order convention (see discipline reference).

### 5. Presentations

Split **Invited Talks** (keynotes, seminars — prestige signal) from **Conference Presentations** (posters/oral). Format: "Talk Title," Venue, City, Date.

### 6. Grants & Funding

List agency, mechanism, your role (PI/Co-PI/Co-I), title, dates, total amount and your lab's share. Separate **Awarded** / **Pending**. Listing "Not Funded" is field-specific — see the discipline reference.

### 7. Teaching Experience

Course number, title, role (Instructor of Record / TA / Guest Lecturer), institution, dates, enrollment, any new course development. Summarize teaching evaluations if strong.

### 8. Mentoring

Graduate students (name, expected year, dissertation, current position), postdocs, undergrad researchers. Placement outcomes matter to committees.

### 9. Service

Profession (editorial boards, review panels, organizing) / University (committees, search committees) / Department (advising, seminar coordination).

### 10–11. Memberships & Honors

Professional societies with years; honors in reverse-chronological order (fellowships early-career, awards later).

### 12. References — follow the application's instructions

**Follow the application instructions: include named references when customary or requested.** Many academic applications collect letters via portals or dossier systems (e.g., Interfolio) rather than the CV — in those cases list the dossier service instead. Where references do go on the CV, "References available upon request" reads poorly to most faculty search committees — don't emit it.

```
REFERENCES
[Name], Professor of [Field], [University]
  [email]
[Name], [Title], [Institution]
  [email]
[Name], Program Director, [Funder/Institution]
  [email]
```

Rules:
- 3–5 referees when listed; for early-career, the dissertation advisor is conventionally first
- Full name, title, affiliation, email (phone optional) for each
- Ask each referee before listing them; confirm they'll write a strong letter
- If the user cannot name referees yet, use [PLACEHOLDER] and ask — don't fall back to "available upon request"

## Full Chronology — Know Which Document You're Writing

- **Application CV:** complete record (degree years, full appointments, all publications) — committees expect it.
- **Public faculty page:** a curated highlight version; full CV usually linked as a PDF.
- **Grant biosketch (NSF/NIH):** its own format — page-limited, role-relevant products only; never reuse the application CV verbatim.

## CV Length Guidelines

| Career Stage | Expected Length |
|--------------|-----------------|
| Graduate Student | 2-4 pages |
| Postdoc | 3-6 pages |
| Early Career Faculty | 5-10 pages |
| Mid-Career Faculty | 10-20 pages |
| Senior Faculty | 15-30+ pages |

The CV grows throughout a career. Don't pad, but don't artificially constrain length.

## Output Format

```markdown
# ACADEMIC CV STRUCTURE FOR [NAME]

## Recommended Section Order
1. [Section] ... (per position type)

## Section Content
### Education
[formatted]
### Publications
[field-appropriate style]
### [Other sections]
[formatted]

## References Section
[3-5 named referees with title/affiliation/email — placeholders if TBD]

## Formatting Notes
- [Field-specific conventions from references/discipline-conventions.md]

## Things to Add/Update
- [ ] [Missing item]
```

## Academic CV Checklist

- ✅ Position is genuinely academic (faculty/postdoc/research) — otherwise use an industry skill
- ✅ Education complete with advisors, dissertation, committee
- ✅ Publications formatted per field convention, name bolded, DOIs included
- ✅ Grants with role, dates, amounts; Awarded/Pending separated
- ✅ Teaching and service documented
- ✅ References: named per application instructions (or dossier service listed) — no "available upon request"
- ✅ Consistent formatting, reverse-chronological (usually), no unexplained gaps
