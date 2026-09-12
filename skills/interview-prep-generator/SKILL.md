---
name: interview-prep-generator
description: Use when preparing for a job interview — STAR stories, predicted questions, senior/staff SWE loops, salary and departure-question guardrails, and a per-role prep plan.
---

# Interview Prep Generator

## When to Use This Skill

Use this skill when the user wants to:
- Prepare for a job interview
- Practice answering interview questions
- Create STAR stories from their experience
- Anticipate questions for a specific role
- Mentions: "interview prep", "prepare for interview", "STAR stories", "interview questions", "behavioral questions"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, and achievement must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-leaning line, identical everywhere.

**Confidential search (employed users):** Ask before naming the current employer in outreach or public artifacts; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

## Interview Preparation Framework

### Phase 1: Role Analysis
- Extract likely questions from job description
- Identify skills that will be tested (for senior/staff SWE: system design is usually the decisive loop — see references/question-banks.md)
- Research the company's interview format (onsite vs. video vs. async screen; coding vs. take-home)

### Phase 2: Story Banking
- Convert resume bullets into STAR stories (method below; examples in references/star-examples.md)
- Cover the core competencies: leadership, problem-solving, collaboration, achievement, failure/growth
- For senior/staff SWE add: org-influence stories, killing-your-own-project, build-vs-buy-vs-deprecate, disagreement-with-a-principal
- Build full (2 min), short (60s), and one-liner (15s) versions of each

### Phase 3: Mock Preparation
- Practice answers aloud, timed
- Prepare questions to ask (staff-appropriate set below)
- Rehearse the departure narrative and salary answer — these are now guardrail items, not improvisation

## The STAR Method

- **S**ituation: Set the context (1-2 sentences)
- **T**ask: Describe your responsibility (1 sentence)
- **A**ction: Explain what YOU did (2-3 sentences)
- **R**esult: Share the outcome with metrics (1-2 sentences)

```
SITUATION: "At [Company], we faced [specific challenge/context]..."
TASK: "I was responsible for [specific ownership]..."
ACTION: "I [specific action 1], [specific action 2], and [specific action 3]..."
RESULT: "As a result, [quantified outcome]. This led to [business impact]."
```

Delivery time: 90 seconds to 2 minutes. Full worked examples (including a staff-engineering story with scale metrics): `references/star-examples.md`.

## Hard Guardrails: Departure & Career-Retrospective Questions

These are the highest-risk moments in any interview. Non-negotiable rules:

1. **Never mention legal disputes, HR complaints, settlements, or any negative framing of a former employer** — not if asked directly, not as context, not "off the record." Not even euphemistically.
2. **Never bad-mouth a former employer, manager, or team**, even when the interviewer invites it ("sounds like a tough situation there"). They assume you'll talk about them the same way next.
3. **Neutral, rehearsed departure narrative** — same one line for every departure, everywhere, forward-leaning:

   ```
   "I'm proud of what we built — [one concrete thing]. I'm looking for [scope/growth this role offers], and the timing lined up."
   ```

   Rehearse it until it's boring. Rehearsed ≠ robotic; it means it survives pressure.
4. **Cap the resume walkthrough at the last 10-15 years.** "Walk me through your resume" is not an invitation to narrate 25 years — it's an age proxy and it bores interviewers. Cover the last 3-4 roles in depth, then one line: "...and earlier roles in [domain X] and [domain Y]." If probed further, one sentence per role, maximum.
5. **If asked directly about a dispute or complaint** (illegal in many places, still happens): one neutral sentence, no detail, redirect to the role — "That's resolved and behind me; I'd rather talk about what I'd build here." Do not elaborate, do not correct the record, do not express grievance.
6. **"What would you do differently in your career?"** — answer with a professional choice (a technology bet, a scope decision), never a person, employer, or conflict.

## Compensation (pay-transparency era)

Pay-transparency laws are now in force in MA (2025), CA, CO, NY, WA and roughly 20 other states; asking about compensation and leveling is expected professional behavior, not a faux pas. Several of these states also **ban employers from asking salary history**.

- **The posted range is the anchor.** Research it before the interview (JD, Levels.fyi, Blind). If none is posted where one is legally required, that's a question to ask.
- **Never volunteer salary history.** Not from prior roles, not "what are you making now." If asked (and it's not in a banned jurisdiction), redirect: "I'd rather focus on the value of the role — what's the range budgeted?" You are never obligated to disclose history.
- **If asked for expectations:** give a researched range anchored to the top of the market band, stated plainly:

  ```
  "Based on the posted range and my research, I'm targeting [upper half of band] — [specific scope evidence] is why."
  ```

- **Never say "I'm flexible on compensation"** as an opener — it cedes the only leverage senior candidates have. Flexibility on *structure* (base/equity split) is fine; vagueness on *level* is not.
- Asking the interviewer "What's the band for this level?" is a strong question, not an impolite one.

## Handling Difficult Questions

### "What's your greatest weakness?"

**Formula:** Real, bounded weakness + the concrete behavioral change you've made + evidence the fix works. A humble-brag ("I'm too detail-oriented") fails instantly with senior interviewers.

```
"Early on as a lead, I under-communicated strategic context — my ICs got
tactical direction without the why, and I lost two good engineers' engagement
before I understood why. I now run monthly context-setting sessions where I
walk through the business picture, and my teams' retention and survey scores
since have been the best of my career."
```

Pick a real weakness whose fix you can demonstrate. If you can't name the fix, pick a different weakness.

### "Why are you leaving your current job?"

Neutral, brief, forward-looking (see guardrails above):

```
"I've learned a lot at [Company] — [one concrete pride point]. I'm looking
for [scope this role clearly offers], and the timing lined up."
```

### "Tell me about a time you failed"

Real failure + what you learned + how you applied it since. The failure must actually be a failure (a shipped mistake, a missed signal, a wrong bet) — not a disguised triumph. Full example in references/star-examples.md.

## Question Banks

Full question banks — behavioral by competency, role-specific (including the staff/senior SWE bank), standard questions, and questions to ask at staff level — live in `references/question-banks.md`. Highlights:

**Staff/senior SWE loop (decisive rounds):**
- System design prompts (the decisive loop at staff level)
- Org-influence probes: "Tell me about changing a decision you didn't control."
- "Tell me about killing your own project."
- Build vs. buy vs. deprecate reasoning
- Disagreement with a principal/director engineer

**AI-tool norms in 2025-26 coding rounds:**
- Ask the interviewer their AI-tool policy **before** the round (recruiter or scheduling email): allowed freely? allowed with disclosure? prohibited?
- If allowed: use it like a senior engineer — for boilerplate and API recall, not for the actual problem-solving; narrate your reasoning either way, because the interview is testing judgment, not typing.
- If undisclosed-but-used is against their policy, don't — it's an integrity screen, and companies increasingly check (live reasoning, follow-up questions that expose it).
- In take-homes, disclose AI assistance exactly per instructions; over-disclosure is safe, under-disclosure is a rescinded offer.

**Async video screens (HireVue and similar):**
- Treat as a one-take presentation: prepare 4-5 core stories in the STAR short format, rehearse aloud
- Look at the camera, not the screen; plain background, decent light
- Answer, then stop — rambling past the timer is the most common failure
- Retakes (where allowed) are for technical flubs, not for polishing charm

## Questions to Ask (staff-appropriate)

- "How do architecture decisions actually get made here — who signs off, and what happens when two staff engineers disagree?"
- "What did the last big technical bet here get wrong, and what did it cost?"
- "What's a system here you'd deprecate tomorrow if you could, and why can't you?"
- "How does this role influence roadmap vs. execute it?"
- "What happened to the last person in this role?"

**Skip:** anything answerable by their website, yes/no questions, and compensation mechanics in the first interview (that's the recruiter conversation — see the compensation section for how to handle it when it comes up).

## Output Format

```markdown
# INTERVIEW PREP: [POSITION] AT [COMPANY]

## Role Analysis
**Format:** onsite / video / async screen — confirm platform
**Decisive loop:** [e.g., system design for staff SWE]
**Key competencies:** 1. [C] — evidence: [from JD]

## Predicted Questions
### High probability
1. [Question] → story: [name]
### Guardrail questions (rehearse verbatim)
- Departure narrative: [one line]
- Resume walkthrough cap: last 10-15 years + "earlier roles in X/Y"

## STAR Story Bank
### Story 1: [Name]
**Use for:** [competencies]
**S/T/A/R:** [with confirmed metrics]
**60s version:** [summary]

## "Tell Me About Yourself" Script
[2 minutes, scope-framed — no cumulative-years framing]

## Salary Answer (if asked)
Anchor: [posted range / research] → [prepared range answer]

## Questions to Ask
1. ...

## Red Flags to Avoid
- Don't mention: [disputes, complaints, settlements — ever]
- Don't criticize: [former employers]
- Don't walk through: [roles older than ~15 years, except one line]
```

## Implementation Checklist

1. ✅ Analyze job description for competencies and loop format
2. ✅ Create 8-10 STAR stories covering all competencies (≥1 with scale metrics for engineering)
3. ✅ Write "tell me about yourself" pitch (scope-framed, 2 minutes)
4. ✅ Rehearse the departure narrative and salary answer verbatim
5. ✅ Prepare answers for likely questions (use references/question-banks.md)
6. ✅ Research the company and its interview format
7. ✅ Confirm interview format (onsite / video / async) and test the platform beforehand
8. ✅ Prepare staff-appropriate questions to ask
9. ✅ Practice out loud, timed
10. ✅ Send a 3-sentence thank-you email within 24h: (1) thanks + one specific discussion point from the conversation, (2) one sentence tying your experience to what you heard, (3) forward-looking close ("looking forward to next steps"). Reference a real exchange — generic thanks read as automated.
