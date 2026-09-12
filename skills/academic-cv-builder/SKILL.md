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

**Truthfulness:** Every claim, publication, grant, course name, and metric must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a detail is missing, insert [PLACEHOLDER] and ask. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation.
**Privacy & age signals:** Academic CVs conventionally include degree years and full chronology — the "omit graduation years" rule for industry resumes does NOT apply here; academic search committees expect complete records. Still never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral line used identically everywhere.
**Confidential search (employed users):** Ask before naming a current search or confidential application; academic job-market candor norms differ, but follow the user's instruction.

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
Email: email@university.edu | Phone: (555) 123-4567
Web: yoursite.edu | ORCID: 0000-0000-0000-0000
```

### 2. Education

```
EDUCATION
Ph.D. in Molecular Biology, Stanford University, 2019
  Dissertation: "Title"
  Advisor: Dr. Jane Smith
  Committee: Dr. A, Dr. B, Dr. C
M.S. in Biology, UC Berkeley, 2015
B.S. in Biochemistry, UCLA, 2013 (Summa Cum Laude)
```

Include all degrees reverse-chronologically, dissertation title, advisor, committee (PhD), honors, relevant certificates.

### 3. Research/Academic Positions

```
ACADEMIC APPOINTMENTS
Assistant Professor of Biology, University of Michigan, 2022-Present
Postdoctoral Fellow, MIT, 2019-2022 (Advisor: Dr. John Doe)
Graduate Research Assistant, Stanford University, 2014-2019
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

### 12. References — named, never "available upon request"

**On academic CVs, always list 3–5 named referees with title and affiliation. "References available upon request" is a disqualifying-cliché on academic CVs — never emit it.**

```
REFERENCES
Dr. Jane Smith, Professor of Biology, Stanford University
  smith@stanford.edu
Dr. John Doe, Principal Research Scientist, MIT
  doe@mit.edu
Dr. [Name], Program Director, [Funder/Institution]
  [email]
```

Rules:
- 3–5 referees; for early-career, the dissertation advisor is conventionally first
- Full name, title, affiliation, email (phone optional) for each
- Ask each referee before listing them; confirm they'll write a strong letter
- If a dossier service (e.g., Interfolio) is used, list it here instead
- If the user cannot name referees yet, use [PLACEHOLDER] and ask — don't fall back to "available upon request"

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
- ✅ References: 3–5 named referees with titles/affiliations — no "available upon request"
- ✅ Consistent formatting, reverse-chronological (usually), no unexplained gaps
