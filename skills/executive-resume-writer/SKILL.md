---
name: executive-resume-writer
description: Use only for C-suite, VP, or board resume targets — never senior IC roles; emphasizes strategic leadership, P&L, and board positioning
---

# Executive Resume Writer

## When to Use This Skill

Use this skill when the user:
- Is applying for C-suite, VP, or board roles
- Has 15+ years of experience in senior leadership
- Needs to emphasize strategic leadership over tactical skills
- Mentions: "executive resume", "C-suite", "VP resume", "senior leadership", "board", "executive search"

**GATE — executive targets only.** This skill is for genuine C-suite/VP/board candidacy. Do NOT use it for senior individual contributors (staff/principal engineers, senior PMs, senior designers) — their resumes should stay achievement-technical and 1-2 pages; use `resume-section-builder` instead. A "senior" title alone is not an executive role.

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Contact info: name, phone, email, city/state, optional links — never street address, DOB, photo. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-looking line, identical everywhere (resume, interviews, references).

**Confidential search (employed users):** Ask before naming the current employer anywhere semi-public; offer blind variants. Never publish employer-confidential metrics without a confidentiality pass.

## Executive Resume Philosophy

| Standard Resume | Executive Resume |
|-----------------|------------------|
| Lists skills | Demonstrates leadership brand |
| Shows tasks | Shows strategic impact |
| Focuses on "what" | Focuses on "so what" |
| 1-2 pages | 2-3 pages (executive-search specific — see below) |
| Keywords for ATS | Story for decision-makers |
| Individual contributions | Organizational impact |

## Executive Resume Structure

```
1. Executive Profile/Summary
2. Core Competencies (Leadership Themes)
3. Career Highlights / Key Achievements
4. Professional Experience
5. Board & Advisory Roles
6. Education & Executive Development
7. Industry Recognition (optional)
```

### Length Guidelines
- VP/SVP: 2 pages
- C-Suite: 2-3 pages
- Board CV: can be longer
- **Note:** 2-3 pages is an executive-search convention. If the target is a tech company hiring an exec into a VP+ role through a normal process (not a retained search firm), expect the tech norm of 1-2 pages — bias toward 2.

## Executive Profile Section

Replaces the standard summary. Communicates your **leadership brand**.

### Format
```
[TITLE/FUNCTION] EXECUTIVE

[Leadership brand statement - who you are as a leader]

[2-3 sentences on your track record with scope/scale]

[What you're known for / unique value proposition]
```

### Example
```
CHIEF OPERATING OFFICER | P&L LEADERSHIP | OPERATIONAL SCALING

Growth-focused operations executive with 15+ years scaling B2B technology companies from $50M to $500M+ in revenue. Known for building high-performance teams, operational excellence, and creating scalable infrastructure that enables rapid growth.

Track record includes 3 successful exits, 2 IPO preparations, and leading organizations of 500+ employees across 6 countries. Expertise in operational strategy, M&A integration, and digital transformation in SaaS and enterprise software environments.

Core philosophy: Build repeatable processes that scale while maintaining the agility that drives innovation.
```

## Core Competencies Section

Frame as leadership themes rather than skills lists.

```
LEADERSHIP COMPETENCIES

Strategic Growth        | M&A Integration          | Digital Transformation
P&L Management ($500M+) | Global Team Leadership   | Board Relations
Operational Excellence  | Change Management        | Investor Relations
```

## Career Highlights Section

Biggest achievements upfront, before chronological experience.

```
CAREER HIGHLIGHTS

• [Achievement 1 with metrics]
• [Achievement 2 with metrics]
• [Achievement 3 with metrics]
• [Achievement 4 with metrics]
```
(Metrics must be the user's real, defensible numbers.)

## Experience Section for Executives

### The Executive Bullet Formula

**[Leadership Action] + [Strategic Initiative] + [Business Outcome at Scale]**

### Key Elements for Executive Experience

**Always include:**
- Company context (revenue, employees, stage)
- Reporting structure / span of control
- P&L or budget responsibility
- Strategic scope

**Metrics to emphasize:** revenue growth ($ and %), profitability (margins, EBITDA), cost reduction, team size and development, geographic expansion, M&A activity, exit outcomes.

## Board & Advisory Section

```
BOARD & ADVISORY POSITIONS

Board of Directors | TechStartup Inc. | 2022 - Present
$50M ARR B2B SaaS company. Chair of Compensation Committee.

Advisory Board | VentureStudio | 2020 - Present
Supporting portfolio companies with operational strategy and GTM execution.

Board Observer | AcquiredCo (acquired by BigTech, 2023) | 2021 - 2023
Provided operational guidance through $200M acquisition process.
```

## Executive-Specific Considerations

### Emphasize Change With Proof
Executives are hired to change things, not maintain them. Show what changed because of you, before/after states, and scale of impact.
**Story formula:** "Inherited [situation]. Implemented [strategic change]. Achieved [outcome]."

### Show Leadership Philosophy
Hint at **how** you lead: "Known for building consensus across diverse stakeholder groups"; "Leads with data-driven decision making while maintaining strategic flexibility."

### Handle Tenure Carefully
**Short tenures:** frame around specific missions — "Brought in to lead post-merger integration"; "Recruited for turnaround; completed in 18 months."
**Long tenures:** show progression and reinvention — "Promoted through 4 roles over 12 years."

### Confidential Information
**Do:** use percentage improvements when absolutes are confidential; use ranges for revenue/headcount.
**Don't:** share proprietary strategies, name confidential targets, or reveal undisclosed financials.

## Executive Resume Tone

### Credible Language for Executives
**Strategic action verbs (credible, checkable):**
- Led, Drove, Built, Scaled, Established, Negotiated
- Spearheaded, Orchestrated, Steered, Directed
- Restructured, Integrated, Launched

Avoid hype verbs — "Revolutionized", "Transformed", "Changed the game" — they read as inflation and invite skepticism from boards and search firms who will verify every claim. Prefer precise, boring-but-true verbs paired with real numbers: "Grew", "Reduced", "Delivered".

**Leadership framing:**
- "Led organization through..."
- "Built and scaled..."
- "Established vision for..."
- "Negotiated and secured..."

### What to Avoid
- ❌ Tactical/operational language (managed, handled, assisted)
- ❌ First person pronouns (I, my, me)
- ❌ Jargon without context
- ❌ Generic statements without proof
- ❌ Hype verbs that can't be verified

## Executive Search Considerations

**Your resume may be seen by:** executive recruiters, board members, PE/VC partners, CEOs and CHROs.

**Optimize for:** quick scanning by busy executives, clear career-progression narrative, obvious leadership brand, credible and verifiable achievements.

**Remember:**
- Retained executive-search firms often check references before interviews — that is executive-search-firm-specific practice, not universal. Tech companies and most other employers check references last, after final interviews. Don't assume early-stage reference needs outside retained search.
- Your resume will be fact-checked
- Relationships and reputation matter; the resume opens doors, relationships close deals

## Output Format

```markdown
# EXECUTIVE RESUME

## Executive Profile
[Full executive profile section]

## Core Competencies
[Formatted competency grid]

## Career Highlights
[4-6 top achievements with metrics]

## Professional Experience

### [Most Recent Role]
[Full executive role writeup]

### [Previous Role]
[Full executive role writeup]

## Board & Advisory
[Board positions]

## Education & Development
[Degrees and executive education — no graduation years by default]

---

## Positioning Notes
- Key narrative theme: [The story your resume tells]
- Leadership brand: [What you're known for]
- Differentiator: [What sets you apart]
```
