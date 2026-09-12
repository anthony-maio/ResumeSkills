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

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Contact info: name, phone, email, city/state, optional links — never street address, DOB, photo. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-looking line, identical everywhere (resume, interviews, references).

**Confidential search (employed users):** Ask before naming the current employer anywhere semi-public; offer blind variants. Never publish employer-confidential metrics without a confidentiality pass.

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
- A photo matters — profiles without one get substantially fewer recruiter views. Ignore unsourced multiplier claims ("21x more views") — no verifiable source backs that number.

### 2. Background Banner
- 1584 x 396 px, professional design or industry-related image
- Options: company brand (if allowed), industry imagery, clean abstract, personal brand statement
- Avoid busy patterns that fight the photo

### 3. Headline (Most Important for Searchability)

**Character limit:** 220. **Formula:** [Role] | [Key Expertise] | [Value Proposition]

❌ Weak: "Looking for opportunities" / "Unemployed" / "Open to work" / "Student at University"

✅ Strong — staff/principal SWE:
```
Staff Software Engineer | Distributed Systems & Platform Engineering | Payments APIs at [X]M+ req/day

Principal Engineer | Go, Kubernetes, AWS | Led platform re-architecture serving [X]00+ internal engineers

Staff Engineer → Team Lead flexible | Backend Systems | Design reviews, mentoring, incident command
```

✅ Strong — other roles:
```
Senior Product Manager | B2B SaaS | 0→1 Products from Concept to $10M ARR

Data Scientist | Machine Learning & Analytics | Turning Data into Business Decisions
```
(All metrics must be the user's real numbers — placeholders mark where.)

**Keyword strategy:** exact title variants recruiters type ("Staff Software Engineer", "Platform Engineer"), key skills/tools, industry terms, certifications.

### 4. About Section

**Position:** About now renders near the top of the profile — treat it as prime real estate, not a footer.

- 2,600 char limit; aim 1,500-2,000 (3-5 paragraphs)
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
TechCorp Inc. · Full-time
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
- **Pin your top 3:** the first three skills in your list display pinned at the top of the profile — make these your three strongest, most-endorsed, most-searched skills and gather endorsements there first
- Include job-specific skills, tools, methodologies, and industry terms
- Skip soft skills as list entries ("Leadership") — show them in Experience instead

### 7. Featured Section
Portfolio pieces, published articles, talks, media coverage, key posts. Renders prominently — keep 3-6 strong items, refreshed as work evolves.

### 8. Recommendations
- Target 5-10 quality recommendations; for senior ICs, a mix of managers, peers, and engineers you mentored
- Give recommendations first; ask specific people with suggested talking points right after a shared success

## Keyword Optimization

1. Pull terms from 5-10 job posts for the target role
2. Mirror profiles of people already in the target role
3. Place keywords: headline (highest weight), About (naturally repeated), Experience descriptions, Skills
4. Exact phrases matter more than density; recent activity boosts ranking

## Recruiter Visibility Settings

### Open to Work
- Configure: target titles, locations, start date, job types
- **Default for employed users: "Recruiters only"** (discreet, no badge)
- **Warning:** the "All LinkedIn members" option adds the public green #OpenToWork frame on your photo. It is instantly recognizable — including to your current employer's recruiters and colleagues — and is widely read as an active job-search signal. Choose it only deliberately (e.g., departure already announced)

### Profile visibility
- Show full profile to connections and recruiters
- Turn off "share profile edits" while job hunting (edit notifications broadcast activity)

### Creator mode — retired
Creator mode was removed as a separate toggle in February 2024. Do not instruct anyone to "turn on creator mode" — follows, newsletters, and analytics are now standard profile features available to everyone.

## Visibility Levers That Still Matter in 2026

Completeness and cadence, condensed:
- **Core completeness:** photo, custom headline, current role with a real description, About (1,500+ chars), skills filled toward the 100 cap (top 3 pinned), location + industry set — complete profiles rank higher in recruiter search
- **Posting:** 1-2 substantive technical posts per month (deep-dives, incident write-ups, architecture lessons). This is enough — influencer cadence (3-5x/week) is unnecessary and reads as content-marketing for individual contributors
- **Commenting:** thoughtful comments in your niche a few times a week — on posts by people in your target role/companies — often generates more recruiter attention than posting, and puts your headline in front of the right audience
- **Recent activity boosts search ranking** — the posting + commenting combo above is what keeps you warm

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

### Skills to Add (and top 3 to pin)
[List of skills to add; the 3 to pin and why]

## Visibility Settings
- Open to Work mode recommended: [Recruiters only / public] + why
- Other settings to change: [List]

## Action Items
1. [ ] Update headline
2. [ ] Rewrite About section
3. [ ] Update current role description
4. [ ] Add skills toward 100 cap; pin top 3
5. [ ] Request recommendations
6. [ ] Refresh Featured section
7. [ ] Set Open to Work visibility
```

## Resume-to-LinkedIn Sync

**Keep the same:** real achievements and metrics, titles and dates, core skills, career narrative.
**Expand:** more detail and context per role, more bullets, personality and voice.
**Adjust:** tone more conversational, keywords broader than one job posting, add a contact CTA.
