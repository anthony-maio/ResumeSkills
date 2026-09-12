---
name: application-form-filler
description: Use when filling out job application form fields on Greenhouse, Lever, Ashby, Workday, or any ATS — tailored answers from the candidate's CV, plus safe handling of sensitive and attestation fields.
---

# Application Form Filler

## When to Use This Skill

Use this skill when the user wants to:
- Answer specific questions on a job application form
- Fill out text fields on Greenhouse, Lever, Ashby, Workday, or any ATS
- Write responses to "tell us about yourself" or "why do you want to work here" prompts
- Get clean, copy-pasteable answers to application questions
- Mentions: "fill this out", "what do I write here", "answer this question", "application form", "form field"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

## Core Principle

Application form answers should be direct and specific — not a cover letter crammed into a text box. Each field has a purpose. Answer that purpose clearly, then stop.

**The answer should feel like:** A real person typed it, not a template was filled in.

## Sensitive Fields (read this section before touching any form)

These appear on nearly every Workday/Greenhouse application. Mishandling them ranges from harmful to legally binding. When in doubt, stop and ask.

**1. EEO voluntary self-identification (race, gender, veteran status, disability, and the 40+ age bracket):**
- **Always ask the user; never auto-fill.** Even if the user answered identically on a previous form, confirm each time.
- Note they are **voluntary**, used for compliance reporting, and can be declined ("prefer not to say") with no effect on the application.

**2. Work-authorization and criminal-history attestations:**
- Read the question **verbatim** to the user and require **explicit confirmation** before answering.
- Never infer, never paraphrase, never "fill in what they obviously meant." These are legally binding attestations; an inaccurate yes/no can be grounds for rescinding an offer or firing later.
- If the wording is ambiguous, surface the exact wording and let the user decide — for ambiguous criminal-history wording, suggest they get advice rather than guess.

**3. Desired salary / compensation expectations:**
- **The user's number only. Never generate, suggest a default, or "estimate market rate" into the field.**
- If the user has no number yet, say so and leave the field to them — you can offer to research posted ranges as a separate exercise, but the answer they submit is theirs.
- In pay-transparency jurisdictions (CO, CA, NY, WA, MA and others), the posted range is the anchor; the user decides where in it to land.

**4. Date-of-birth and graduation-date fields:**
- Flag any DOB or graduation-year field to the user as an **age disclosure** before filling it. DOB is almost never legitimately required at application stage; graduation years are a soft age proxy. Let the user choose to answer, skip, or omit (many forms allow "prefer not to say" or leaving the year blank).

**5. AI-usage attestations ("Did you use AI tools to prepare this application?"):**
- **Never answer on the user's behalf.** That's the user's call — answering truthfully is a policy attestation, not a writing task.
- Ask the user directly, answer exactly what they say, no editorializing.

**6. "Have you applied here before?" / "Do you know anyone at this company?":**
- Honesty-sensitive and often verifiable in the ATS. Ask the user; never guess "No" as a default. If they know an employee, get the exact name and relationship — referral tracking is a real pipeline.

## Knockout-Filter Warning (numeric and rating fields)

Some numeric/rating fields are **knockout filters**: the ATS auto-rejects candidates who self-rate below a threshold or whose years-of-experience dropdown is under the JD bar.

- **Never inflate.** A false "expert" rating collapses in the technical screen.
- **Don't undercount either.** The honest answer isn't always the narrowest one — but it must be true. If asked "years of experience with SQL," the truthful figure is years working with SQL specifically, or years in roles where SQL was load-bearing — ask the user which framing is accurate. **Never borrow years from unrelated technologies** to clear a bar; that's a false answer that collapses in the screen.
- **Flag the risk:** if the user's honest answer sits right at or just under an apparent bar (e.g., 7 years against a "8+ years" dropdown), say so explicitly — "this field may auto-reject; here's what you're answering and why" — and let them decide.
- For dropdowns that only offer coarse brackets ("5-7", "8-10"), the user picks the bracket their honest total falls in.

## Before Answering

Always read:
1. **The job description** — mirror its language and priorities
2. **The candidate's CV/profile** — pull real projects, roles, and metrics
3. **The specific question** — answer exactly what was asked, not what you wish was asked

If the user hasn't provided a CV or JD, ask for them before writing.

## Question Types and How to Handle Each

### Type 1: Experience/Background Questions

**Examples:**
- "How many years of experience do you have with [technology]?"
- "Describe your experience with [domain]"
- "What backend frameworks have you used?"

**Format:**
```
[Technology/skill] — [X years]. [One sentence on what you used it for, with a
specific project or context]. [Optional: secondary tools in the same category].
```

**Rules:**
- Lead with the most used/relevant technology
- Give years honestly — don't inflate; check the knockout-filter guidance above so you don't undercount
- Anchor every claim to a real project or role
- For "describe experience" questions: 2-4 sentences max, one project per sentence
- If experience is indirect (adjacent domain), say so and pivot to what is relevant

### Type 2: Why This Company / What Interests You

**Format:**
```
[Specific thing about the company/role that's genuinely interesting — not generic].
[How that connects to something the candidate has actually worked on].
[Optional: one line on why this domain, not just this company].
```

**Rules:**
- Must be specific to this company — no boilerplate
- Research the company before answering if needed
- Connect to real work, not aspirations
- Keep it under 150 words for a form field
- Don't repeat the JD back to them

### Type 3: Portfolio / Work Samples

**Format:** List projects with one-line descriptions and links, most relevant first:

```
[Project Name] ([live URL] | [github URL]) — [one line: what it is and one
proof point]. [Stack if relevant].
```

**Rules:**
- Only include projects relevant to the role; don't pad to look prolific
- Always include links (live demo > GitHub > nothing)
- If the project has paying users or measurable usage, say so — once
- Project names must come from the user's CV only — never from a previous example

### Type 4: Technical Skill Questions

For open-text fields:
```
[Primary skill] — [X years]. [Specific use: what you built with it, in what context].
[Secondary skill] — [X years]. [Same].
[Note any relevant gaps honestly].
```

For rating/dropdown fields: follow the knockout-filter guidance above — honest level, never inflated, never undercounted, risk flagged when near the bar.

### Type 5: Open-Ended / "Tell Us About Yourself"

**Format:**
```
Current role + what you do there (1 sentence).
Relevant prior experience, briefly (1 sentence).
What you're looking for / why this role (1-2 sentences — specific to the company).
Optional: one project or side work that's relevant (1 sentence).
```

**Rules:**
- Start with current role, not education
- Keep to 100-200 words for most form fields
- End on the forward-looking note (what you want, not where you've been)
- No trait statements ("I'm passionate about...") — just facts and projects

### Type 6: Situational / Behavioral Questions

**Format:** Condensed STAR (no labels, just flow)
```
[Context in one sentence]. [What you specifically did — 2 sentences]. [Outcome
with a metric if possible — 1 sentence].
```

**Rules:**
- Be specific — name the project, the tech, the team size
- Don't generalize ("I always approach problems by...")
- Keep to 150-250 words
- First-person, active voice throughout
- End with the result, not the lesson learned (save that for interviews)

### Type 7: AI-Experience Questions ("Describe your experience with AI/LLMs")

**Rules:**
- Describe **real system-building experience factually**: what was built, what the user's specific contribution was, what's production vs. prototype. Never inflate prototype work into "production ML experience."
- If the user has no AI experience, say so plainly — fabricating AI experience is the single easiest claim to falsify in a 2026 interview loop.
- Mirror the JD's actual AI demands (check the job-description-analyzer's AI-washing notes): "used an LLM API in a feature" ≠ "built training/eval pipelines."

### Type 8: Opinion / Vision Questions

**Format:** Answer with a genuine opinion. Pick one or two things and explain the reasoning briefly.

**Rules:**
- Have an actual point of view — vague answers are forgettable
- Ground opinions in domain knowledge or real experience
- Keep to 100-150 words
- Don't hedge everything — commit to a view, acknowledge it's one perspective

## ATS Quirks

- **Plain text survives:** no markdown, no bullets pasted from word processors — use plain sentences or "-" dashes; markdown syntax renders as literal characters in most ATS text boxes.
- **Workday multi-step forms** lose unsaved answers on back-navigation; fill in one pass or save at each step.
- **Greenhouse custom questions** often have character limits (frequently ~500-1000 chars); check before drafting 250 words.
- **Required dropdowns** force an answer where you'd prefer to skip — if the honest answer isn't an option, tell the user rather than picking the closest wrong one.

## Output Format

Always wrap the answer in a plain code block so it's clean to copy-paste:

```
[Answer text here]
```

If providing multiple answers (one per field), use separate code blocks with a label above each:

**Years of React experience:**
```
6 years. Used it across [Project A] (a real-time analytics dashboard), an
internal design-system library, and several client projects. Next.js where
SSR was needed.
```

**Describe your backend experience:**
```
...
```

## Length Calibration

| Field type | Target length |
|------------|---------------|
| Single-line text | 1 sentence |
| Short answer | 2-4 sentences |
| Long answer / textarea | 100-250 words |
| "Describe your experience" | 150-300 words |
| "Tell us about yourself" | 100-200 words |
| Portfolio / links section | List format, no prose |

When in doubt, shorter is better. Recruiters skim form answers. The goal is to be clear and memorable, not comprehensive.

## Pre-Submit Checklist

Before the user submits:
1. ✅ Every factual claim traces to the user's CV or explicit statement
2. ✅ Sensitive fields (EEO, attestations, salary, DOB/graduation dates, AI-usage, applied-before/knows-anyone) were answered by the user, not generated
3. ✅ Numeric/rating answers: honest, not undercounted, knockout risk flagged where relevant
4. ✅ List any fields left for the user to answer personally, with why

## Common Mistakes to Avoid

**Repeating the JD:** ❌ "I am interested in this role because you are looking for someone to build scalable backend systems..." → ✅ "What caught my attention was the real-time constraint — healthcare data at milliseconds latency is a different class of problem than most backend work."

**Generic trait claims:** ❌ "I am a fast learner who thrives in collaborative environments" → ✅ just describe the actual work — the traits come through.

**Over-qualifying:** ❌ "While I may not have exactly 5 years, I believe my experience..." → ✅ "The role mentions 5 years — I'm at 3, but the systems I've shipped are production-facing."

**Listing without context:** ❌ "React, Vue, Angular, Next.js, TypeScript, Node.js..." → ✅ "React is my primary frontend framework — 6 years across [Project A] and several client projects. Vue and Angular for about 3 years each, mostly dashboards and admin tooling."

**Padding to fill space:** ❌ adding irrelevant projects to look prolific → ✅ include only what's relevant to this specific role.

**Auto-filling sensitive fields:** ❌ selecting an EEO category, guessing a work-authorization answer, typing a salary number → ✅ ask, read attestations verbatim, and let the user answer.
