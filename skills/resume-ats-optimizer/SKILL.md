---
name: resume-ats-optimizer
description: Use when checking whether a resume will parse cleanly and cover a specific JD's requirements — extractable-text verification, risk-tiered formatting, and evidence-ranked keyword coverage (no fake scores).
---

# Resume ATS Optimizer

## When to Use This Skill

Use this skill when the user wants to:
- Check whether their resume will parse in an Applicant Tracking System (ATS)
- Compare resume coverage against a specific job description
- Understand why applications aren't getting responses
- Mentions: "ATS", "not getting interviews", "resume not working", "keyword match", "optimize resume"

For visual layout and fonts, defer to resume-formatter (canonical). This skill covers parseability verification and JD coverage.

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Contact info: name, phone, email, city/state, optional links — never street address, DOB, photo. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-looking line, identical everywhere.

**Confidential search (employed users):** Ask before naming the current employer in outreach or public artifacts; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass — prefer percentages, ranges, anonymized phrasing.

## How ATS Actually Works (2026 reality)

Modern ATS platforms (Greenhouse, Lever, Workday, iCIMS) **parse and store** resumes; they do not auto-reject on formatting. Auto-rejection is rare and happens via knockout questions (work authorization, location, license requirements) — not two-column layouts. Recruiters then **search by keyword** and review ranked lists.

The real risks, in order:
1. **Unparseable files** — scanned/image PDFs, text embedded in graphics
2. **Missing searchable keywords** — true skills the user has, phrased so search finds them
3. **Knockout questions** — answer these carefully in the portal, not the resume

Context that lowers the stakes: referrals, recruiter outreach, and Easy Apply with a strong profile largely bypass keyword screening. Keyword coverage matters, but it is not the bottleneck folklore makes it. Never cite rejection-percentage statistics — the popular ones are debunked myths.

## Parseability Verification (actually run this)

Don't guess whether a resume parses — extract its text and check:

```bash
pdftotext resume.pdf - | head -80
```

(Available in poppler-utils; `python -m pip install pdftotext` or use `pdftotext` via WSL. For .docx, unzip and read `word/document.xml`, or convert with `libreoffice --headless --convert-to pdf`.)

**Pass criteria — all must survive extraction:**
- [ ] Name and contact info present and in order
- [ ] Every job title and employer recognizable
- [ ] Every date range intact (e.g., "Jan 2020 – Mar 2023")
- [ ] Section headers recognizable ("Experience", "Education", "Skills")
- [ ] Skills list intact, not scrambled or merged

If text extraction scrambles the layout (columns interleaving, dates detached from titles), simplify the layout and re-run. If contact info and dates survive a text-extraction pass, parsing will almost certainly work.

## Formatting Risk Tiers

**Never (high risk, no payoff):**
- ❌ Scanned or image-based PDFs (no text layer)
- ❌ Text embedded in images/graphics/charts
- ❌ Skill bars, infographic ratings, text in logos

**Low risk, verify with the paste test:**
- Headers/footers — major platforms extract them; still keep contact info in the body as belt-and-suspenders
- Simple tables and two-column layouts — fine on Greenhouse/Lever/Workday if the paste test passes (text extraction keeps names/dates/sections in order)
- Columns for skills lists — acceptable; verify extraction order reads sensibly

**Always safe:**
- ✅ Single column, standard headers, standard bullets (•, -), consistent MM/YYYY dates
- ✅ Standard section names: "Professional Experience", "Education", "Skills", "Summary"

**File format:** .docx or text-based .pdf. File name: `FirstName_LastName_Resume.pdf`. Full formatting canon lives in resume-formatter.

## JD Coverage Analysis (qualitative, no scores)

Do not compute or invent numeric match scores — there is no universal threshold, vendor weighting varies, and a fabricated "65%" drives keyword-stuffing anxiety. Report evidence instead.

### Step 1: Extract JD requirements
List each *requirement* from the JD (not just keywords): responsibilities, required skills, nice-to-haves, seniority signals.

### Step 2: Classify coverage per requirement

| JD Requirement | Coverage | Evidence in resume |
|---|---|---|
| e.g., "LLM inference experience" | **Verbatim** | "Reduced LLM inference cost 38%..." |
| e.g., "stakeholder management" | **Synonym** | "Aligned 4 product teams on..." |
| e.g., "Kubernetes at scale" | **Absent** | — |

Three coverage levels only: **Verbatim** (JD's term appears), **Synonym** (equivalent phrasing — flag exact term for consideration), **Absent** (no evidence).

### Step 3: Report and recommend

- Verbatim → no action
- Synonym → suggest adding the JD's exact term *if truthfully the user's skill* ("aligned 4 teams" can also say "stakeholder alignment across 4 teams")
- Absent → ask the user: do you have this? If yes, where? If no, don't add it

**Placement principle:** each critical term should appear where a reader expects it — once in skills, once inside a concrete achievement. Never repeat a term solely to raise density; there is no keyword-density ranking factor on mainstream platforms, and repetition reads as spam to the recruiter who opens the file.

## Analysis Output Format

```markdown
# ATS PARSE & COVERAGE REPORT

## Parseability (from pdftotext run)
- Text extraction: Pass/Fail
- Name/contact intact: Y/N
- All titles + employers + dates intact: Y/N
- Layout notes: [scrambled column order? detached dates?]

## Formatting Risks
- Tier-1 (must fix): [image PDFs, text in graphics — or none]
- Tier-2 (verify, likely fine): [tables/columns that passed the paste test]

## JD Requirement Coverage
| Requirement | Verbatim | Synonym | Absent |
|---|---|---|---|
| [req 1] | ✓ | | |
| [req 2] | | ✓ ("your phrasing" ≈ "JD term") | |
| [req 3] | | | ✗ — ask user |

## Recommended Changes
1. [Synonym → exact term, only if truthful]
2. [Absent → question for the user, never auto-add]
3. [Any Tier-1 formatting fix + re-run paste test]
```

No "overall score", no "estimated new match %" — coverage decisions belong to the human.

## Level-Specific Advice

### Mid-level engineers
- Lead bullets with scale (users, QPS, data volume) and the JD's stack names
- One strong bullet per requirement beat; don't pad

### Senior engineers
- Each recent role: 3–5 bullets showing system ownership and outcomes
- Mirror the JD's domain vocabulary (e.g., "platform", "developer productivity", "inference")

### Staff/principal engineers
- Recruiters screen for **scope and org-level influence**, not keyword count
- Coverage language that matters: "across N teams", "org-wide", "adopted by N product lines", "defined technical strategy for..."
- **Certifications rarely influence screening** at this level at major tech companies — don't add AWS/Azure certs to chase keywords; noise at best
- A **publications / patents / talks** line carries far more weight than any certification: "Publications: 6 papers on applied LLM serving (NeurIPS, arXiv); talk, KubeCon 2024" — searchable, verifiable, differentiating
- Design-review ownership, migration leadership, and strategy-doc authorship are the searchable signals of staff scope

### Executive level
- Strategic keywords, board experience, P&L size, org size — plus the staff-track signals above if the role is technical

For Healthcare / Marketing / Business / Finance industry keyword sets, see `references/industries.md`.

## Edge Cases

### Career changers
- Coverage table will show many "Absent" — resist the urge to bridge gaps with borrowed keywords; surface transferable evidence and ask before adding any new claim

### Recent graduates
- Education becomes the keyword surface (coursework, tools); internships count as experience

### Employment gaps
- Years-only dates are acceptable; freelance/consulting lines carry keywords truthfully

## Implementation Checklist

1. ✅ Run text extraction (pdftotext or equivalent) on the actual file
2. ✅ Verify name, contacts, titles, employers, dates all extract
3. ✅ Build the requirement coverage table (verbatim/synonym/absent)
4. ✅ Ask the user about every "absent" before suggesting anything
5. ✅ Suggest exact-term swaps only for confirmed-synonym cases
6. ✅ Fix Tier-1 formatting issues; re-run extraction after any layout change
7. ✅ Report qualitatively — no invented scores
