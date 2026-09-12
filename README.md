# Resume Skills for AI Agents

A collection of agent skills for resume optimization, job applications, and career development — tuned for senior/staff-level software and AI engineering candidates, with 2026-accurate ATS/pay-transparency/equity guidance and strict truthfulness/privacy guardrails.

Fork of [Paramchoudhary/ResumeSkills](https://github.com/Paramchoudhary/ResumeSkills), substantially revised. Every skill now includes a shared **Candidate Guardrails** block (no fabricated metrics, no age-proxy signals, confidential-search rules for employed candidates, neutral departure narratives), trigger-style frontmatter descriptions, and progressive disclosure (worked examples live in each skill's `references/` directory).

## What changed in this fork (vs upstream)

**Myth removal & 2026 accuracy**
- Deleted the debunked "75% of resumes are rejected by ATS" claim and all fake numeric match-score formulas (replaced with evidence-ranked keyword coverage: verbatim / synonym / absent)
- Removed keyword-density ("2–4x per term") stuffing advice; placement-based keyword guidance instead
- Risk-tiered formatting rules + a runnable paste-test (extract PDF text and verify it survives) instead of categorical bans on tables/columns
- Pay-transparency leverage built in: posted-range anchoring, state salary-history-ban handling, MA/CA/NY/WA/CO/etc. table in `salary-negotiation-prep/references/pay-transparency-states.md`
- Startup equity valued with an expected-value framework (409A vs preferred, dilution, liquidation preference, 83(b), ISO/AMT, single- vs double-trigger RSUs) — see `offer-comparison-analyzer/references/equity-math.md`
- LinkedIn skill updated: skills cap 100 (not 50), creator mode retired Feb 2024, Open-to-Work defaults to Recruiters-only for employed users

**Senior/staff-engineer content**
- Staff-level bullet patterns (scope → decision → org-level outcome), scope-ladder diagnostic (features → systems → multi-team programs → org strategy)
- Publications/patents/talks/open-source section formats; certifications demoted (rarely matter at staff screening)
- Staff/senior SWE interview question bank (system design loops, org-influence probes, AI-tool disclosure norms), engineering-voice cover-letter hooks, senior cold-email variants
- AI/ML metric categories (eval benchmarks, inference cost per 1K requests, serving latency, quality lift)

**Truthfulness & privacy guardrails (all skills)**
- Never invent or "estimate" metrics: ask-first flow, `[PLACEHOLDER]` discipline, marked estimates with logged derivations
- No age proxies: graduation years omitted by default for senior candidates, tenure capped at "15+" or omitted, 10–15-year experience horizon
- Confidential search: ask before naming the current employer; blind variants; NDA gate before publishing any employer-confidential metric
- Neutral departure narratives everywhere (resume, cover letters, interviews, reference briefings); never reference disputes or bad-mouth employers
- Sensitive ATS fields (EEO self-id incl. age bracket, work-authorization attestations, desired salary) are never auto-filled
- References: excluded from current employer by default, consent required for shared contact channels, departure-narrative briefing step

**Gated skills** (kept for other audiences, scoped so they don't misfire): `executive-resume-writer` (C-suite/VP/board only), `career-changer-translator` (genuine career changers only; functional format restricted + warned), `academic-cv-builder` (faculty/postdoc only), `creative-portfolio-resume` (creative fields only).

## Available Skills

| Skill | Description |
|-------|-------------|
| [resume-ats-optimizer](/skills/resume-ats-optimizer) | Verify a resume parses cleanly and covers a JD's requirements — evidence-ranked coverage, no fake scores |
| [resume-bullet-writer](/skills/resume-bullet-writer) | Rewrite weak bullets into achievement statements; staff-level patterns |
| [job-description-analyzer](/skills/job-description-analyzer) | Evidence-ranked fit assessment and application strategy for a posting |
| [resume-tailor](/skills/resume-tailor) | Tailor an existing resume to a specific posting; truthful versioning |
| [cover-letter-generator](/skills/cover-letter-generator) | Cover letters and short application notes; when to skip the letter entirely |
| [linkedin-profile-optimizer](/skills/linkedin-profile-optimizer) | LinkedIn optimization with employed-candidate privacy defaults |
| [interview-prep-generator](/skills/interview-prep-generator) | STAR stories, staff-level SWE question banks, sensitive-question guardrails |
| [salary-negotiation-prep](/skills/salary-negotiation-prep) | Negotiation with pay-transparency leverage and salary-history legality |
| [tech-resume-optimizer](/skills/tech-resume-optimizer) | Senior/staff software & AI engineering resumes; publications, OSS, scope framing |
| [offer-comparison-analyzer](/skills/offer-comparison-analyzer) | Offer comparison with equity EV math and a "vs. staying put" baseline |
| [career-changer-translator](/skills/career-changer-translator) | For genuine career/industry changers only |
| [resume-quantifier](/skills/resume-quantifier) | Add real metrics — ask-first, confidentiality pass, no invented numbers |
| [resume-formatter](/skills/resume-formatter) | ATS-friendly formatting with paste-test verification |
| [portfolio-case-study-writer](/skills/portfolio-case-study-writer) | Case studies with an NDA/confidentiality gate; SWE and AI/ML examples |
| [academic-cv-builder](/skills/academic-cv-builder) | For faculty/postdoc/academic targets only |
| [reference-list-builder](/skills/reference-list-builder) | Reference lists with consent, freshness, and departure-narrative rules |
| [executive-resume-writer](/skills/executive-resume-writer) | For C-suite/VP/board targets only |
| [resume-version-manager](/skills/resume-version-manager) | Master/tailored version tracking; git-based workflow for engineers |
| [creative-portfolio-resume](/skills/creative-portfolio-resume) | For creative fields only; risk-tiered ATS compatibility |
| [resume-section-builder](/skills/resume-section-builder) | Section formats by career stage, with a senior-IC track |

## Installation

```bash
# Clone and copy to your agent's skills folder
git clone https://github.com/anthony-maio/ResumeSkills.git
mkdir -p ~/.claude/skills   # or ~/.hermes/skills, ~/.codex/skills, etc.
cp -r ResumeSkills/skills/* ~/.claude/skills/
```

Each skill directory is self-contained (SKILL.md + optional `references/`), so you can also copy just the skills you want.

## Supported AI Agents

Claude Code, Hermes Agent, Codex CLI, Cursor, Windsurf, Gemini CLI, and other agents that load the SKILL.md convention.
