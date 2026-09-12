---
name: resume-version-manager
description: Use when the user has multiple resume versions to manage — master resume, tailored per-company versions, tracking, and update workflow
---

# Resume Version Manager

## When to Use This Skill

Use this skill when the user:
- Has multiple resume versions to manage
- Needs to track tailored resumes
- Wants to maintain a master resume
- Is applying to many different roles
- Mentions: "resume versions", "master resume", "different versions", "track resumes", "which resume"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-looking line, identical everywhere (resume, interviews, references).

**Confidential search (employed users):** Ask before naming the current employer anywhere semi-public; offer blind variants. Never publish employer-confidential metrics without a confidentiality pass.

**Outbound-version privacy:** Every version you actually send carries only: name, phone, email, city/state, and optional links — never a street address, DOB, or photo. Never attach reference lists to outbound resumes; track references separately (see `reference-list-builder`) and share them only on request after the employer asks. The master resume may hold fuller detail internally, but outbound copies get the minimal contact set.

## Core Capabilities

- Create and maintain a master resume (source of truth)
- Track tailored resume versions
- Organize versions by role/industry/seniority
- Streamline updates and prevent version confusion

## The Version Management Problem

**Pain points:** "Which version did I send to Company X?", "Where's my most recent resume?", "15 files, no idea which is best", "I keep tailoring from different bases."

**Solution:** one master resume, organized tailored versions, clear naming, a consistent update workflow.

## Master Resume Concept

A comprehensive document holding ALL experiences, every bullet you've written, every achievement/project/skill — even material that won't fit on one page. It's the pull-source for tailoring.

```markdown
# MASTER RESUME - [YOUR NAME]
Last Updated: [Date]

## CONTACT (internal master only — outbound copies get the minimal set)
## PROFESSIONAL SUMMARY VERSIONS (one per role type)
## ALL SKILLS (by category)
## PROFESSIONAL EXPERIENCE
### Company | Title | Dates
• All bullets (leadership / technical / results / collaboration variants)
• Keywords this experience covers
## EDUCATION (full history internally)
## CERTIFICATIONS
## PROJECTS
## VOLUNTEER / ADDITIONAL
## REFERENCES TRACKED SEPARATELY (names, consent dates, last-contacted — never on the resume)
```

## Experience Horizon Rule

**Default: detail the most recent 10-15 years on tailored versions; compress everything older to a single line.**

- Roles within the horizon: full treatment (bullets, metrics, keywords)
- Roles beyond the horizon: one line each, or one collective line — "Earlier career: [Role] at [Company], [Role] at [Company] (20XX-20XX)". No bullets, no dated detail.
- Reasons: relevance decay (15-year-old tech stacks and titles rarely match current postings), length control, and age-signal hygiene — a detailed 25-year history broadcasts an age proxy while adding little.
- Exceptions: a genuinely relevant older role (e.g., the one startup the target company knows) may stay detailed — decide per application, from the master.

## File Organization System

```
Resume/
├── Master/
│   └── LastName_Master_Resume.docx
├── Tailored/
│   ├── ProductManagement/
│   │   └── LastName_PM_Google_Jan2024.pdf
│   ├── Engineering/
│   │   └── LastName_SWE_Stripe_Feb2024.pdf
│   └── General/
├── CoverLetters/
└── Applications/
    └── ApplicationTracker.xlsx
```

**Naming:** `[LastName]_[Role/Type]_[Company]_[Date].pdf` — e.g. `Smith_SWE_Stripe_Feb2024.pdf`.

## Version Categories

Tailored versions vary along three axes — the *content guidance* for what each role type/industry emphasizes lives in `resume-section-builder` (section order, skills formatting, examples per role type). Use this skill for the management layer: which versions exist, what pulls from the master, and where they went.

- **By role type:** e.g. SWE vs. PM vs. Data — different summary + skills emphasis
- **By industry:** tech/startup (direct, achievement-focused) vs. enterprise (structured, comprehensive) vs. finance (conservative, credentialed)
- **By seniority:** IC (execution + technical depth) vs. manager (leadership + impact) vs. executive (strategy + P&L)

## Application Tracking

| Company | Role | Version Used | Date Applied | Status | Notes |
|---------|------|--------------|--------------|--------|-------|
| Google | PM | PM_Google_Jan | 1/15/24 | Interview | 2nd round 2/1 |
| Startup | PM | PM_General | 1/20/24 | Rejected | Too senior |

Also track: application method (portal/referral/direct), follow-up dates, contacts. Keep a separate reference tracker (who, consent date, last contacted) — see `reference-list-builder`.

## Update Workflow

**Update the master immediately for:** new job/promotion, major completed project, new skills/certs, significant achievements.

**Quarterly:** add recent wins, refresh metrics, prune outdated material, re-check the experience horizon (roles crossing the 10-15 year line get compressed).

**Master → tailored:**
```
1. Copy master (never edit master for an application)
2. Analyze the job description
3. Apply the experience horizon (10-15 yrs detailed, earlier = one line)
4. Select relevant bullets; choose the summary variant
5. Reorder skills; add job-specific keywords
6. Strip outbound contact info to the minimal set
7. Trim to length; save with naming convention; update tracker
```

## Git-Based Workflow (for technical users)

If the user is comfortable with git, a repo beats folders:

- **Markdown master** (`resume.md`) in a **private repo** — single source of truth, plain-text diffs show exactly what changed and when
- **Per-company tailored versions**: generate from the master on a branch or tag per application — `git checkout -b apply/stripe-2024-02` or tag `stripe-2024-02` after generating
- **Generated PDFs**: build via pandoc/typst/HTML template, never hand-edited; PDFs are build artifacts, optionally ignored or kept per-tag
- **History = tracker**: `git log` / `git tag` answers "exactly what did I send Stripe, and when" for free; keep a lightweight `APPLICATIONS.md` in-repo for status
- **Privacy:** private repo only — resumes are dense PII. If the user open-sources anything (theme/template), keep the resume content itself out

## Common Scenarios

- **Similar roles:** one well-tailored base per role type; minor per-company tweaks; track which variation went where
- **Different role types:** separate bases, all pulling from the same master
- **High volume:** 2-3 strong category versions + a general version; deep tailoring reserved for top choices
- **Career transition:** transition-focused version + original-industry version as backup (see `career-changer-translator`)

## Best Practices

**DO:** always work from master; consistent naming; track what went where; date files; keep master current; cloud backup; archive (don't delete) old versions.

**DON'T:** edit master directly for an application; vague names like `resume_final_v2`; multiple "master" files; send street address/DOB/photo; attach references to outbound resumes; let pre-horizon roles bloat tailored versions.

## Output Format

```markdown
# RESUME VERSION MANAGEMENT

## Master Resume Status
**Last Updated:** [Date] | **Location:** [path or repo]
**Experience Horizon Check:** [roles >15 yrs compressed? which crossed recently?]

## Active Versions
### Role Type: [e.g. Engineering]
**Base:** [file/branch]
| Company | File/Tag | Date | Status |
|---------|----------|------|--------|

## Update Queue
- [ ] [e.g. Add Q4 project results to master]

## Recommended Actions
1. [Action]
```

## Checklist

- ✅ Master resume exists and is current
- ✅ Experience horizon applied (10-15 yrs detailed; earlier = one line)
- ✅ Naming convention consistent; tracker maintained
- ✅ Outbound copies carry only phone/email/city-state/links
- ✅ References tracked separately, never attached
- ✅ All versions pull from the same master
- ✅ Backup (cloud or private git repo) in place
- ✅ Old versions archived, not deleted
