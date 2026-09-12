---
name: linkedin-profile-optimizer
description: Use when the user wants to optimize their LinkedIn profile for searchability, recruiter visibility, or resume-to-LinkedIn sync
---

# LinkedIn Profile Optimizer

## When to Use This Skill

Use this skill when the user wants to:
- Optimize their LinkedIn profile for job searching
- Improve LinkedIn visibility and searchability
- Sync their resume with their LinkedIn profile
- Attract recruiters and job opportunities
- Mentions: "LinkedIn", "LinkedIn profile", "optimize LinkedIn", "LinkedIn headline", "recruiter"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

## LinkedIn vs. Resume: Key Differences

| Aspect | Resume | LinkedIn |
|--------|--------|----------|
| Length | 1-2 pages | Unlimited |
| Tone | Formal | More conversational |
| Keywords | Job-specific | Industry-wide |
| Audience | One specific employer | All recruiters |
| Updates | Per application | Always current |
| Personality | Minimal | Show more |

## Profile Section Optimization

### 1. Profile Photo
- Professional headshot (not casual), face ~60% of frame, good lighting, high resolution
- Neutral or branded background; attire appropriate to the industry
- A photo matters — the no-photo rule in the guardrails is a US *resume* norm; LinkedIn is a different artifact where a professional photo is the norm, and profiles without one likely get fewer recruiter views. Ignore unsourced multiplier claims ("21x more views") — no verifiable source backs that number.

### 2. Background Banner
- 1584 x 396 px, professional design or industry-related image
- Options: company brand (if allowed), industry imagery, clean abstract, personal brand statement
- Avoid busy patterns that fight the photo

### 3. Headline (Most Important for Searchability)

**Character limit:** 220. **Formula:** [Role] | [Key Expertise] | [Value Proposition]

❌ Weak: "Looking for opportunities" / "Unemployed" / "Open to work" / "Student at University"

*Fictional example for structure only — never copy its facts into user output.*

✅ Strong — staff/principal SWE:
```
Staff Software Engineer | Distributed Systems & Platform Engineering | Payments APIs at [X]M+ req/day

Principal Engineer | Go, Kubernetes, AWS | Led platform re-architecture serving [X]00+ internal engineers

Staff Engineer → Team Lead flexible | Backend Systems | Design reviews, mentoring, incident command
```

✅ Strong — other roles:
```
Senior Product Manager | B2B SaaS | 0→1 Products from Concept to $[X]M ARR

Data Scientist | Machine Learning & Analytics | Turning Data into Business Decisions
```
(All metrics must be the user's real numbers — placeholders mark where.)

**Keyword strategy:** exact title variants recruiters type ("Staff Software Engineer", "Platform Engineer"), key skills/tools, industry terms, certifications.

### 4. About Section

**Position:** About now renders near the top of the profile — treat it as prime real estate, not a footer.

- 2,600 char limit; ~1,500-2,000 characters (3-5 paragraphs) is a common goal if you have that much substance — an optional range, not a default
- Only ~300 characters show before "see more" — lead with the hook
- Structure: hook → who you are/what you do → achievements & specialties → what you want → searchable skills line → call to action

**Staff/principal SWE example:**
```
I build the platforms other engineers ship on.

At [Company] I lead a [X]-engineer platform group owning the delivery infrastructure for [X]0+ services. Recent work: cut p99 latency [X]% on the checkout path, led the migration from [old] to [new] for [X] teams, and stood up the incident-review practice that dropped repeat Sev1s to [X]/quarter.

Before that: backend engineer at [Previous Company], where I owned [system] through its [X]x growth and learned to love boring, well-instrumented systems.

What I do best:
→ Design reviews and technical strategy for cross-team initiatives
→ Mentoring — [X] engineers promoted to senior under my mentorship
→ Turning ambiguous reliability problems into measurable SLOs

Key skills: Distributed Systems, Go, Kubernetes, AWS, Terraform, Observability (Datadog/Prometheus), System Design, Incident Response

Happy to talk platform engineering, reliability, or Staff+ career paths. Reach me at [email].
```

### 5. Experience Section

Longer and more narrative than resume; include media (talks, docs, demos); update continuously.

Per role: title, company, dates, location, 2-3 sentence scope statement, 4-6 achievement bullets, media attachments.

**Staff SWE example:**
```
Staff Software Engineer
[Company] · Full-time
Mar 2022 - Present
San Francisco, CA · Hybrid

Technical leadership for the Platform group: [X] engineers across 3 teams owning delivery infrastructure for the whole engineering org ([X]00 engineers).

• Led re-architecture of the deployment pipeline, cutting median deploy time from [X] to [X] minutes and raising deploy frequency [X]x
• Designed and drove adoption of the service-mesh migration across [X] teams with zero customer-facing incidents
• Owned incident command for Sev1s; overhauled postmortem process, reducing repeat Sev1s by [X]%
• Mentored [X] engineers to promotion; ran the org's design-review forum
• Drove [X]% cost reduction on compute spend through right-sizing and workload scheduling

Skills: Distributed Systems · Kubernetes · Go · Terraform · Observability
```

### 6. Skills Section

**Cap is 100 skills now** (raised from 50) — use it, but stay honest:
- Aim for 30-50 genuinely held, recruiter-searched skills; don't pad to 100
- **Put your strongest skills first.** LinkedIn's UI has at times surfaced the first few skills at the top of the profile — verify the current pinning behavior in the UI rather than assuming it. Order your strongest, most-endorsed, most-searched skills first and gather endorsements there
- Include job-specific skills, tools, methodologies, and industry terms
- Skip soft skills as list entries ("Leadership") — show them in Experience instead

### 7. Featured Section
Portfolio pieces, published articles, talks, media coverage, key posts. Renders prominently — a handful of strong items (3-6 is a common goal, not a rule), refreshed as work evolves.

### 8. Recommendations
- A small bench of quality recommendations (5-10 is a common goal if your network supports it, not a rule); for senior ICs, a mix of managers, peers, and engineers you mentored
- Give recommendations first; ask specific people with suggested talking points right after a shared success

## Keyword Optimization

1. Pull terms from 5-10 job posts for the target role
2. Mirror profiles of people already in the target role
3. Place keywords across headline, About (naturally repeated), Experience descriptions, and Skills — this likely helps recruiter search and comprehension; LinkedIn doesn't publish a stable weighting, so don't treat placement order as a known ranking factor
4. Exact phrases likely matter more than density, and recent activity likely helps visibility — LinkedIn doesn't publish its ranking model

## Recruiter Visibility Settings

### Open to Work
- Configure: target titles, locations, start date, job types
- **Default for employed users: "Recruiters only"** (discreet, no badge)
- **Warning:** the "All LinkedIn members" option adds the public green #OpenToWork frame on your photo. It is instantly recognizable — including to your current employer's recruiters and colleagues — and is widely read as an active job-search signal. Choose it only deliberately (e.g., departure already announced)

### Profile visibility
- Show full profile to connections and recruiters
- Turn off "share profile edits" while job hunting (edit notifications broadcast activity)

### Creator mode — retired
Creator mode was removed as a separate toggle during 2024. Do not instruct anyone to "turn on creator mode" — follows, newsletters, and analytics are now standard profile features available to everyone.

## Visibility Levers That Still Matter in 2026

Completeness and cadence, condensed:
- **Core completeness:** photo, custom headline, current role with a real description, a substantive About section, skills filled toward the cap (strongest first), location + industry set — complete profiles likely rank higher in recruiter search; LinkedIn doesn't publish a stable weighting
- **Posting:** 1-2 substantive technical posts per month (deep-dives, incident write-ups, architecture lessons). This is enough — influencer cadence (3-5x/week) is unnecessary and reads as content-marketing for individual contributors
- **Commenting:** thoughtful comments in your niche a few times a week — on posts by people in your target role/companies — often generates more recruiter attention than posting, and puts your headline in front of the right audience
- **Recent activity likely helps visibility** (LinkedIn doesn't publish a stable ranking model) — the posting + commenting combo above is what keeps you warm

## Output Format

```markdown
# LINKEDIN PROFILE OPTIMIZATION

## Current Profile Assessment
**Completeness:** X%
**Searchability Score:** X/10
**Key Issues:** [List]

## Optimized Sections

### Headline
**Current:** [Their current headline]
**Optimized:** [New headline with keywords]

### About Section
[Full optimized About section text]

### Experience Improvements
**[Company Name]**
- Add: [Suggested additions]
- Modify: [Suggested changes]
- Media to add: [Suggestions]

### Skills to Add (strongest first)
[List of skills to add; which to order first and why]

## Visibility Settings
- Open to Work mode recommended: [Recruiters only / public] + why
- Other settings to change: [List]

## Action Items
1. [ ] Update headline
2. [ ] Rewrite About section
3. [ ] Update current role description
4. [ ] Add skills toward the cap; order strongest first
5. [ ] Request recommendations
6. [ ] Refresh Featured section
7. [ ] Set Open to Work visibility
```

## Resume-to-LinkedIn Sync

**Keep the same:** real achievements and metrics, titles and dates, core skills, career narrative.
**Expand:** more detail and context per role, more bullets, personality and voice.
**Adjust:** tone more conversational, keywords broader than one job posting, add a contact CTA.
