---
name: creative-portfolio-resume
description: Use when the user works in a creative field (design, marketing, writing, photography) and needs a resume that balances visual design with ATS risk management and portfolio integration.
---

# Creative Portfolio Resume

## When to Use This Skill

Use this skill **only for creative fields** — design (graphic, UX, product), marketing/brand, writing/content, photography/video. For software engineering, PM, or general industry resumes, use the dedicated resume skills; a "designed" resume is the wrong tool there.

Use when the user:
- Works in a creative field and wants a visually designed resume
- Needs to balance visual design with ATS compatibility
- Mentions: "creative resume", "designer resume", "visual resume", "portfolio resume"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

## Core Capabilities

- Balance visual appeal with ATS risk
- Design resumes for creative roles
- Integrate portfolio elements with resume content
- Advise on when to use creative vs. traditional formats

## The Creative Resume Dilemma

Creative professionals want to show design skill through the resume, but most applications pass through ATS parsing first. One common answer is a **two-version approach**:

1. **ATS-compatible version** for online applications and job boards
2. **Designed version** for portfolio, networking, direct submissions, interviews

It's an option, not the only fix: a **single accessible PDF** (clean single-column, strong typography, subtle color) is preferable for some channels — recruiters who only ever see one file, or anyone who can't manage version routing. If you keep two versions, **sync both with the master resume** on every update (see `resume-version-manager`); a stale designed version with old dates is worse than one plain resume.

### Use ATS-Compatible Version When:
- Applying through online portals or job boards
- The resume will be parsed by software (or you're unsure)

### Use Designed Version When:
- Networking events, direct email to a hiring manager
- Portfolio website, in-person interviews
- Creative agencies that expect visual resumes
- You're told ATS isn't used

## ATS Risk Tiers (not categorical bans)

Most elements aren't "ATS-banned" — they carry different parsing risk. Match the tier to the version you're building:

**Low risk (usually fine in both versions — still test the actual exported file):**
- ✅ Single-column text flow
- ✅ Standard section headers (Experience, Education, Skills)
- ✅ Bold/italic emphasis, sparing header color
- ✅ Hyperlinks to portfolio
- ✅ Any widely available font (Arial, Calibri, Georgia, Helvetica…)

**Medium risk (designed version only, or ATS version with testing):**
- ⚠️ Two-column layouts — some parsers read across columns and scramble order
- ⚠️ Tables for layout — content may extract out of order
- ⚠️ Icons or small graphics standing in for text (email/phone icons with no text label)
- ⚠️ Skill bars, charts encoding data visually

**High risk (designed version only):**
- 🚫 Key content inside images or text boxes (parser sees nothing)
- 🚫 Header/footer as the only location for contact info
- 🚫 Non-selectable text (outlined type, exported as pure graphics)

### The .txt paste-test (run this on EVERY ATS version)

A necessary smoke test, not sufficient validation — passing it means text extracts in order, not that every parser will read the file cleanly. When the channel is unknown, prefer a **DOCX** export (most reliably parsed) alongside the PDF. Concrete step:
1. Export the resume PDF.
2. Copy-paste all text from the PDF into a plain `.txt` file (or run `pdftotext resume.pdf -`).
3. **Check:** job titles, company names, dates, and skills appear in the correct order, no content missing, no column-interleaving gibberish.
4. If anything is missing or scrambled, fix the layout and re-test. The ATS version isn't done until the .txt output reads cleanly.

## Designed Portfolio Resume

### Design Principles

1. **Show, don't just tell** — the resume IS a design sample; typography and layout demonstrate design thinking.
2. **Clarity over cleverness** — information must stay findable; save experimental work for portfolio pieces.
3. **Brand consistency** — match the portfolio site: consistent palette, unified identity.

### Visual Elements

- **Typography:** headline font (personality) + body font (readable); clear size hierarchy; max 2 families
- **Color:** limited palette (2–3), high contrast, prints acceptably in B&W
- **Layout:** two-column acceptable here; grid-aligned; generous white space; scannable in 6 seconds
- **Accents:** consistent icons, rules, subtle background elements, personal mark

## Creative Field-Specific Guidance

### Graphic Designers
Must show typography, layout/composition, hierarchy, attention to detail. The resume is itself a portfolio piece — clean and sophisticated, with range shown through subtle choices; link to the portfolio for breadth.

### UX/Product Designers
Must show information architecture, user-centered thinking, hierarchy, systematic approach. Scannable, recruiter-focused structure; link to case studies.

### Marketing/Brand
Must show brand thinking, storytelling, strategic communication. On-brand identity, narrative flow, proof points for every claim.

### Writers/Content
Must show writing quality and editing precision. Impeccable copy, strong bullets, zero errors; personality through the writing itself — the design should stay quiet.

### Photographers/Video
Must show visual eye and production quality. Clean, uncluttered layout; strong portfolio link; let the work speak.

## Portfolio Integration

*Fictional example for structure only — never copy its facts into user output.*

On the resume:
```
Portfolio: yourname.com
• Redesigned checkout flow, increasing conversion [USER-CONFIRMED METRIC]%
  Case study: yourname.com/checkout
```

On the portfolio site: offer the designed PDF for download, keep an HTML resume page responsive, and keep both versions in sync with the master resume.

## Tools

Any tool that exports a clean, text-selectable PDF works — InDesign, Figma, Illustrator, Canva, Word, Google Docs. Choose by proficiency, not prestige; verify every export with the .txt paste-test.

## Output Format

```markdown
# CREATIVE RESUME STRATEGY

## Role Type: [Design/Marketing/Writing/Photo-Video] | Industry: [Agency/In-house/Freelance]

## Version Strategy
### Version 1: ATS-Compatible
**Use for:** online applications, job boards
**Format:** .docx + .pdf | **Risk tier:** low only
**Paste-test result:** [pass/fail + fixes made]

### Version 2: Designed
**Use for:** portfolio, networking, direct outreach
**Format:** print-quality .pdf | **Risk tier:** medium/high elements allowed

## Design Specifications
### Typography
- Headline: [font, weight, size] | Body: [font, weight, size]
### Colors
- Primary: [hex/use] | Secondary: [hex/use] | Text: [hex]
### Layout
- Format: [column structure] | Margins: [spec]

## Portfolio Integration
- Main link: [URL] | Case studies to highlight: [list]
```

## Creative Resume Checklist

- ✅ Both versions exist; correct version routed to each channel
- ✅ ATS version passes the .txt paste-test with clean ordered text
- ✅ Design demonstrates relevant creative skill; content still scannable
- ✅ Portfolio prominently linked; identity consistent with the portfolio site
- ✅ Typography, color accessible and print-friendly
- ✅ Content quality matches design quality
