---
name: cover-letter-generator
description: Use when the user needs a cover letter or short application note for a job application — includes the decision of whether a letter is even the right artifact.
---

# Cover Letter Generator

## When to Use This Skill

Use this skill when the user wants to:
- Write a cover letter for a job application
- Create a personalized application note
- Address specific job requirements in letter format
- Mentions: "cover letter", "application letter", "write cover letter", "letter for job"

Use AFTER analyzing the job description (job-description-analyzer) to have clear talking points.

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course, certification, skill, tool, and responsibility must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. Missing number? Insert [USER-CONFIRMED METRIC] and ask. Estimates only on explicit request, marked (~ or range), with a logged derivation.

**Privacy & age signals:** On resumes, omit graduation years by default for senior candidates and never include street address, DOB, or photo (US industry norm; academic CVs and non-US norms differ — follow field conventions there). Frame seniority as scope, not elapsed time; total-years phrasing is the user's choice, not a default. Never mention legal disputes, HR complaints, or settlements; reason-for-leaving is one neutral, forward-looking line, used consistently.

**Confidential search (employed users):** Ask before naming the current employer in any outbound or public artifact; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

**Examples in this skill are illustrative only:** never copy numbers, names, employers, venues, patent numbers, or identifiers from examples into user output.

## Step 0: Decision Gate — Is a Letter Even the Right Artifact?

Before writing, ask:

1. **Is the cover letter field required or optional?**
2. **How senior is the candidate?**

Decision rules:

- **Senior/staff candidate + optional field** → recommend a **3-4 sentence application note** (pasted into the optional field or attached) or **direct outreach to the hiring manager** (see cold-email-writer skill) as the default. Offer the full letter as an alternative; conservative industries (finance, consulting, legal, government) still expect full letters.
- **Required field** → write the letter, but keep it short (see length below).
- **Conservative industries** (finance, consulting, legal, government) → full formal letter remains the norm.

Only write the full letter if the user wants one after hearing the recommendation.

## Length

- **Senior candidates: 150-250 words usually beats 400.** Hiring managers skim; a short, dense letter reads as senior. 
- Mid-level / required-field / conservative industries: 250-350 words max.
- Anything over 400 words is a bug.

## Format Default

**Default: header-free body text** when the letter is pasted into a text box or portal field — salutation through sign-off keeps the word budget on content. **Use the formal letter layout** (sender contact block, date, recipient block) when attaching a PDF, especially for conservative industries.

**Fallback (conservative industries / email attachments only):** formal letter layout — sender contact block, date, recipient block — kept minimal.

## Structure

```
[Salutation — named person if known, else "Dear Hiring Team,"]

Opening: Hook + position + why this company (2-3 sentences)
Body 1: Strongest qualification match — their need + your exact experience + specific result (3-4 sentences)
Body 2: Additional value, and gap handling ONLY if a required gap is confirmed (2-3 sentences)
Closing: Enthusiasm for something specific + call to action (2-3 sentences)

[Sign-off + name]
```

## Opening Hooks (choose one)

Keep exactly one opening in the final letter; the others can be offered as alternatives in the output. Two engineering-voice examples, two PM/general.

**1. Specific Company Knowledge (engineering)**
```
"Your engineering blog's post on migrating the ledger to a region-sharded architecture described exactly the problem I spent last year solving — staged decomposition of a monolith that four teams depended on."
```

**2. Impressive Achievement (engineering)**

*Fictional example for structure only — never copy its facts into user output. If the user's search is confidential, do not name the current employer (see guardrails); use the blind variant below.*
```
"I own the ingestion pipeline that handles [USER-CONFIRMED METRIC] at
[Company / a Series-B fintech — blind variant]; your JD's scale requirements
are the first I've read in months that match the problems I work on daily."
```

**3. Mutual Connection (general)**
```
"[Name] on your [team] team mentioned you're hiring for [role] — having worked with [Name] at [Previous Company] on [domain], I wanted to reach out directly."
```

**4. Industry Insight (PM/general)**
```
"[Company]'s decision to [specific, concrete product move — e.g., open-source the ledger API] tells me you're betting on [specific outcome] — I've spent five years building in [domain] and want to contribute to exactly this."
```

**Opening don'ts:**
- ❌ "I am writing to apply for..." (obvious)
- ❌ "I am the perfect candidate..." (their call, not yours)
- ❌ "I saw your job posting on LinkedIn..." (generic)
- ❌ Starting with "I" when you could start with them or the hook

## Body Paragraphs

**Body 1 — direct match:** [Their top need] + [your exact experience] + [specific result].

Engineering example (illustrative structure — metrics from the user only; blind variant if the search is confidential):

*Fictional example for structure only — never copy its facts into user output.*
```
Your requirement for engineers who've owned systems at scale maps directly to my last four years: I designed and led the migration of payments ingestion from a single-region service to a sharded architecture serving [USER-CONFIRMED METRIC], cutting p99 latency from [baseline] to [new] while four product teams kept shipping on top of it.
```

**Body 2 — broader value + gap handling:**

If there are NO required-skill gaps, add more value (one more relevant achievement or a specific company-research connection).

**Gap handling rules (strict):**
- Address a gap ONLY if (a) the JD lists it as *required*, AND (b) the user has confirmed their actual status with that skill.
- **Never volunteer an unasked weakness.** Raising a gap the JD doesn't require — or that no one asked about — undermines the application, especially for senior candidates.
- **Never insert course names, self-study claims, or activities the agent hasn't been told about.** If the user's status is unknown, ask before writing anything.
- Use truthful generic phrasing when confirmed:

```
"My data work has been in [confirmed area]; I ramp quickly on new tooling — [confirmed example of having done exactly that]."
```

## Closing

End with confidence and a clear next step:

```
"I'd welcome the chance to discuss how the [specific system/domain] experience maps to your [specific initiative]. Thank you for considering my application."
```

**Closing don'ts:** passive "I look forward to hearing from you", "Please find my resume attached" (they know), "at your convenience" desperation.

## Scenarios

**Referral:** lead with it — "[Name] on your [team] suggested I apply."

**Underqualified (by the JD's letter, not reality):** don't apologize; lead with the strongest transferable evidence. One sentence acknowledging the stretch at most.

**Overqualified / leveling down:** address motivation with *scope*, not elapsed time: "I want to return to hands-on [domain] work with direct system ownership" — NOT "after 20 years..." (age proxy; also unnecessary).

**Career change:** "While my background is in [field], my work in [transferable skill] translates directly to [new role] via [specific connection]." Any upskilling claims must be user-confirmed facts, not generated course names.

**Unknown hiring manager:** "Dear Hiring Team," or "Dear [Department] Team," — never "To Whom It May Concern."

## Industry Notes

- **Tech/Engineering:** reference their stack/systems honestly, link GitHub/portfolio if the user has one.
- **Finance/Consulting/Legal:** formal tone, full letter layout, credentials early — this is the header fallback case.
- **Startup:** casual, scrappy, growth-minded. **Enterprise:** process and scale experience.

## Output Format

```markdown
# APPLICATION LETTER FOR [POSITION] AT [COMPANY]

## Decision
- Field: required / optional (→ note if a short application note is recommended instead)
- Length: [N] words

## Letter
[Header-free body text]

## Alternative Opening (optional, one)
[One alternative hook]

## Interview Talking Points
- [2-3 points the letter sets up]
```

## Quality Checklist

1. ✅ Decision gate answered before writing (required field? senior candidate?)
2. ✅ Opens with a hook, not "I am writing to apply"
3. ✅ One specific company-research reference
4. ✅ Experience tied to their stated requirements, with a real metric the user confirmed
5. ✅ No unasked-for gaps, no invented courses/skills
6. ✅ No age proxies (graduation years, cumulative-years framing), no disputes, no negative employer framing
7. ✅ Neutral, forward-leaning language about any departure
8. ✅ Header-free format when pasting; formal layout when attaching for conservative industries
9. ✅ Length appropriate (150-250 for senior; ≤400 always)
10. ✅ Confident, not arrogant; would make you want to interview this person
