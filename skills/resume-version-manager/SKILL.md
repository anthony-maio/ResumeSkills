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

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

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
• Keywords this experience covers + confidentiality tag (public-safe / confidential / needs-confirmation / excluded)
## EDUCATION (full history internally)
## CERTIFICATIONS
## PROJECTS
## VOLUNTEER / ADDITIONAL
## REFERENCES TRACKED SEPARATELY (names, consent dates, last-contacted — never on the resume)
```

## Master Resume Confidentiality

Tag every master-resume entry with a confidentiality field:

- **public-safe** — verified facts that may appear in any outbound version
- **confidential/internal** — employer-confidential metrics, unreleased products, internal infra; redact or anonymize in every outbound version
- **needs-confirmation** — unclear what may be shared; ask before any outbound use
- **legal-sensitive/excluded** — NDA-covered, settlement-related, or dispute material; never appears in outbound versions or talking points

**Mandatory outbound redaction pass (every tailored version):** strip or anonymize anything not tagged public-safe or explicitly confirmed for that application — confidential metrics become percentages or [USER-CONFIRMED METRIC], internal names become anonymized descriptors, legal-sensitive material is removed entirely. Outbound copies carry only the minimal contact set (name, phone, email, city/state, optional links) — never street address, DOB, or photo — and never attach reference lists (tracked separately; see `reference-list-builder`).

## Experience Horizon Guidance (relevance-first)

**Start from the target role's requirements, not a fixed cutoff.** Detail the roles that best evidence fit for the posting; compress older roles when they are no longer relevant or when space requires it. Many senior candidates default to detailing the most recent 10-15 years and compressing everything earlier to a single line — a reasonable default, not a rule.

- Detailed roles: full treatment (bullets, metrics, keywords) — chosen for relevance to the target, not recency alone
- Compressed roles: one line each, or one collective line — "Earlier career: [Role] at [Company], [Role] at [Company] ([YEARS])". No bullets, no dated detail.
- Why compressing helps: relevance decay (old stacks and titles rarely match current postings), length control, and age-signal hygiene — a detailed 25-year history broadcasts an age proxy while adding little
- Exceptions: a genuinely relevant older role (e.g., the one startup the target company knows) may stay detailed — decide per application, from the master

## File Organization System

```
Resume/
├── Master/
│   └── LastName_Master_Resume.docx
├── Tailored/
│   ├── ProductManagement/
│   │   └── LastName_PM_[Company]_[YYYY-MM].pdf
│   ├── Engineering/
│   │   └── LastName_SWE_[Company]_[YYYY-MM].pdf
│   └── General/
├── CoverLetters/
└── Applications/
    └── ApplicationTracker.xlsx
```

**Naming:** `[LastName]_[Role/Type]_[Company]_[YYYY-MM].pdf` — e.g. `Smith_SWE_[Company]_[YYYY-MM].pdf`. (For the file you actually send, see `resume-formatter` for file naming.)

## Version Categories

Tailored versions vary along three axes — the *content guidance* for what each role type/industry emphasizes lives in `resume-section-builder` (section order, skills formatting, examples per role type). Use this skill for the management layer: which versions exist, what pulls from the master, and where they went.

- **By role type:** e.g. SWE vs. PM vs. Data — different summary + skills emphasis
- **By industry:** tech/startup (direct, achievement-focused) vs. enterprise (structured, comprehensive) vs. finance (conservative, credentialed)
- **By seniority:** IC (execution + technical depth) vs. manager (leadership + impact) vs. executive (strategy + P&L)

## Application Tracking

| Company | Role | Version Used | Date Applied | Status | Notes |
|---------|------|--------------|--------------|--------|-------|
| [Company] | PM | PM_[Company]_[YYYY-MM] | [YYYY-MM-DD] | Interview | 2nd round [YYYY-MM-DD] |
| [Company] | PM | PM_General | [YYYY-MM-DD] | Rejected | Too senior |

Also track: application method (portal/referral/direct), follow-up dates, contacts. Keep a separate reference tracker (who, consent date, last contacted) — see `reference-list-builder`.

## Update Workflow

**Update the master immediately for:** new job/promotion, major completed project, new skills/certs, significant achievements.

**Quarterly:** add recent wins, refresh metrics, prune outdated material, re-check the experience horizon (roles that no longer earn their space get compressed).

**Master → tailored:**
```
1. Copy master (never edit master for an application)
2. Analyze the job description
3. Apply the experience horizon (relevance-first: detail what evidences fit; compress what doesn't)
4. Select relevant bullets; choose the summary variant
5. Reorder skills; add job-specific keywords only where supported by confirmed experience — JD keywords with no covering experience are recorded as gaps to address, never inserted
6. Run the outbound redaction pass (confidentiality tags + minimal contact set)
7. Trim to length; save with naming convention; update tracker
```

## Git-Based Workflow (for technical users)

If the user is comfortable with git, a repo beats folders:

- **Markdown master** (`resume.md`) in a **private repo** — single source of truth, plain-text diffs show exactly what changed and when
- **Per-company tailored versions**: generate from the master on a branch or tag per application — `git checkout -b apply/[company]-[YYYY-MM]` or tag `[company]-[YYYY-MM]` after generating
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
**Experience Horizon Check:** [which roles detailed vs. compressed — and why]

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
- ✅ Experience horizon applied relevance-first (irrelevant/older roles compressed)
- ✅ Naming convention consistent; tracker maintained
- ✅ Outbound redaction pass run; copies carry only phone/email/city-state/links
- ✅ References tracked separately, never attached
- ✅ All versions pull from the same master
- ✅ Backup (cloud or private git repo) in place
- ✅ Old versions archived, not deleted
