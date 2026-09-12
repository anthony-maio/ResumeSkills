---
name: resume-formatter
description: Use when laying out, reformatting, or ATS-checking a resume's visual structure — margins, fonts, sections, and a paste-test parseability check.
---

# Resume Formatter

## When to Use This Skill

Use this skill when the user:
- Needs help with resume layout and formatting
- Has a messy or hard-to-read resume
- Wants layout that parses cleanly in ATS
- Mentions: "format resume", "resume layout", "resume design", "clean resume", "professional format"

This is the canonical formatting skill — other resume skills defer here on layout.

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Contact info: name, phone, email, city/state, optional links — never street address, DOB, photo. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-looking line, identical everywhere.

**Confidential search (employed users):** Ask before naming the current employer in outreach or public artifacts; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass — prefer percentages, ranges, anonymized phrasing.

## Formatting Fundamentals

The resume must work for two readers: the parser (extractable text) and the human (6-second skim). Clean, simple formatting serves both — the human skim is usually the stricter constraint.

### Page Length
- **Entry level (0–5 years):** 1 page
- **Mid-level (5–15 years):** 1–2 pages
- **Senior (15+ years):** 2 pages
- **Staff/principal ICs:** 2 pages is standard; page 3 only if publications/patents warrant their own section
- **Executives:** 2 pages (a third only with board/publications content)

### Document Setup
- **Margins:** 0.5"–1" all sides (0.5" minimum)
- **Fonts:** Arial, Calibri, Helvetica (sans) or Georgia, Times New Roman (serif)
- **Sizes:** name 16–20pt, headers 12–14pt, body 10–12pt (never below 10pt)
- **Spacing:** 1.0–1.15 line spacing; 12–16pt between sections

## Parse-Safe Formatting (risk-tiered)

### Never
- ❌ Scanned or image-based PDFs — no text layer, nothing extracts
- ❌ Text embedded in images, graphics, or charts
- ❌ Skill bars / proficiency graphics
- ❌ Essential information conveyed only by color

### Low risk — acceptable, verify with the paste test
- **Simple tables** (e.g., contact info in a row) — fine on major platforms
- **Two-column layouts / columnar skills lists** — acceptable if extraction reads in order
- **Headers/footers** — extractable on major platforms; still keep contact info in the body
- **Bold/italic sparingly, standard bullets (•, -)**

### The Paste Test (run it, don't guess)
Convert the final PDF to text and read it:

```bash
pdftotext resume.pdf - | head -80
```

**Pass:** name, contact, every title, employer, and date range extract intact and in order; sections recognizable. If columns interleave or dates detach from titles, simplify to single-column and re-test. If it passes, parsing will almost certainly work.

### Always safe
- ✅ Single column, standard section headers, consistent MM/YYYY or "Mon YYYY" dates, .docx or text-based .pdf

## Section Organization

### Standard Order
```
1. Contact Information
2. Professional Summary (recommended for senior+)
3. Skills / Technical Skills
4. Professional Experience
5. Publications / Talks / Patents (if any — see tech-resume-optimizer)
6. Education
7. Certifications / Additional
```

### Section Headers (parser-recognizable)
PROFESSIONAL EXPERIENCE / WORK EXPERIENCE · EDUCATION · SKILLS / TECHNICAL SKILLS · SUMMARY · PROJECTS · PUBLICATIONS

Format consistently — CAPS with a rule line, or bold title case; pick one.

## Contact Information

```
JOHN SMITH
john.smith@email.com | (555) 123-4567 | linkedin.com/in/johnsmith
San Francisco, CA
```

**Include:** name, professional email, one phone, city/state, LinkedIn, portfolio/GitHub/scholar profiles if substantive.
**Hyperlinks:** show full URLs as visible text (`github.com/johnsmith`), optionally also hyperlinked — the visible text survives parsing even when the link doesn't.

**Exclude:**
- ❌ Full street address
- ❌ Photo, date of birth, marital status
- ❌ Multiple phone numbers, personal social media
- ❌ Graduation years for senior candidates (age proxy — optional after ~10 years of experience)
- ❌ GPA (recent grads only)

## Experience Section

```
COMPANY NAME | City, ST
Job Title | Mon YYYY – Mon YYYY
• Achievement bullet with metrics and results
```

- **Dates:** one consistent format throughout ("Jan 2020 – Present"); avoid full day-level dates
- **Bullets:** 1–2 lines each; 3–6 per role (more for recent roles, 1–2 for roles 10+ years old)
- **Old roles:** compress to a one-line "Earlier experience" entry by default; flag the trade-off to the user

## Skills Section

```
TECHNICAL SKILLS
Languages: Python, TypeScript, SQL
Frameworks: React, FastAPI, PyTorch
Infra: AWS, Docker, Kubernetes, Terraform
```

Columnar/triple-column lists are acceptable — verify with the paste test that the categories and items extract in reading order.

## Education Section

```
EDUCATION
B.S. Computer Science | UC Berkeley
```

For senior candidates: degree, institution; graduation year optional; GPA and coursework omitted.

## Visual Hierarchy (short version)

1. **Name** largest → 2. **Section headers** clear → 3. **Titles/companies** scannable → 4. **Bullets** the detail. Use size, bold, and CAPS for levels; consistent spacing between sections. Good white space separates sections and frames content; bad white space is inconsistency, huge gaps, or half-empty pages.

## Common Mistakes

1. **Wall of text** → bullets, short lines
2. **Inconsistent formatting** → pick one scheme, apply everywhere
3. **Over-creative design** → the real costs are slowed human scanning and possible parse errors on older enterprise portals; for tech roles, senior engineers converge on clean single-column anyway. Creativity goes in the portfolio.
4. **Cramming** → cut content by relevance, not margins
5. **Too sparse** → add detail, widen to 0.5" margins

## File Guidelines

- **Online applications:** .docx (safest) or text-based .pdf
- **Direct send:** .pdf (preserves layout)
- **Naming:** `FirstName_LastName_Resume.pdf` or `FirstName_LastName_Resume_[Role].pdf` — never `resume_final_v2_FINAL.docx`

## Output Format

```markdown
# RESUME FORMATTING REVIEW

## Current Issues
- [Issue 1] ...

## Recommended Changes
### Document Setup
- Margins/Font/Sizes: [current → recommended]
### Section Order
- [current → recommended + why]
### Parse-Safety Fixes
- [Tier-1: image text, etc.]
- [Tier-2: verify tables/columns via paste test]

## Paste Test Result
- Extraction: Pass/Fail; notes on column order, detached dates

## Before/After
- [Sketch of key changes]
```

## Quick Checklist

- ✅ Length matches seniority (2 pages standard for senior/staff)
- ✅ Standard font, 10–12pt body
- ✅ Consistent formatting and dates
- ✅ No scanned/image PDFs, no text in graphics
- ✅ Tables/columns passed the paste test
- ✅ Contact info in body, city/state only, no age proxies (grad years, GPA for seniors)
- ✅ Full URLs visible as text
- ✅ Saved as .docx or text-based .pdf, properly named
