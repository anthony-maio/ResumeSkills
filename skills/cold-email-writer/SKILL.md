---
name: cold-email-writer
description: Use when writing cold outreach emails to hiring managers, founders, or recruiters — specific, human, not a pitch deck.
---

# Cold Email Writer

## When to Use This Skill

Use this skill when the user wants to:
- Write a cold outreach email to a hiring manager, founder, or recruiter
- Reach out about a job opening they weren't referred to
- Introduce themselves to a company they want to work at
- Mentions: "cold email", "reach out", "intro email", "outreach", "contact hiring manager"

## Candidate Guardrails (always apply)

**Truthfulness:** Every claim, metric, course name, certification, and skill listed must come from facts the user provided or confirmed. Never generate specifics the user hasn't stated. If a number is missing, insert [PLACEHOLDER] and ask — never invent or silently 'estimate' one. If the user explicitly requests an estimate, mark it (~ or range) and log the derivation so they can defend it in an interview.

**Privacy & age signals:** Never volunteer age proxies — graduation years (omit by default for senior candidates), '20+ years' framing (cap at '15+' or omit), early-career dates. Frame seniority as scope, not elapsed time. Never mention legal disputes, HR complaints, settlements, or negative framings of former employers; reason-for-leaving is one neutral forward-leaning line, identical everywhere.

**Confidential search (employed users):** Ask before naming the current employer in outreach or public artifacts; offer blind variants. Never publish employer-confidential metrics without an explicit confidentiality pass.

## Core Principle

Cold emails fail because they sound like cover letters. The goal is to sound like a smart person who genuinely noticed something specific about the company — not a candidate broadcasting their credentials.

**The email should feel like:** A colleague mentioning something interesting they read, not a sales pitch.

## The Template Structure

### Subject

Two options — pick based on recipient:

```
Quick intro — [First Name Last Name]
```
```
[Role] — [First Name Last Name]
```

The name-only subject is understated and works with founders who read everything. The role-context subject raises open rates with busy engineering leaders and inboxes filtered by recruiters — a bare stranger's name pattern-matches to sales spam there. Default to the role-context variant when writing to an EM or in-house recruiter about a specific opening.

### Opening — The Hook (2-3 sentences)
Start with what genuinely pulled the candidate in. Must be specific to this company — not a generic compliment.

```
I just came across [Company] and ended up spending more time on it than I expected.
[One specific thing that caught their attention — a stat, a product decision, a market insight from the JD or website]
```

**What makes a good hook:** a specific number or stat from their materials; a product decision that shows domain understanding ("you're building from scratch alongside underwriters, not just distribution"); a technical insight from the JD ("improving the data infrastructure for LLM usage, not just the model layer").

**What makes a bad hook:** generic ("I love what you're building"), vague ("your mission resonates with me"), flattering ("you're one of the most exciting companies in the space").

### Location Disclosure (if needed)
If location is a potential friction point (international candidate, or the role is tied to an office), disclose it early and casually:

```
Before you read further, I should mention I'm based in [country / city, and remote/relocation status].
Happy to figure out the rest if there's a real fit.
```

US-domestic candidates generally don't need this unless the role requires relocation or hybrid presence — then one line on willingness.

### Experience Gap (if applicable)
If the role lists more years than the candidate has, acknowledge it briefly and redirect:

```
The role mentions [X] years of experience — I'm at [Y], but the work I've
shipped is production-facing and I'd rather you judge that directly.
```

### The Body — Who They Are (3-5 sentences)
Current role → relevant past → one or two projects. Keep it contextual, not a list.

```
A bit about me: I currently work at [Company], [one line on what the company does],
where I [what they actually do there — not a job title]. Before that I worked
with teams in [region], mostly around [relevant domain].

On the side I've been building [Project] ([link if applicable]) — [one line: what
it is and one proof point like "got to paying clients" or "20K downloads"].
```

**Rules:**
- Mention work as context, not as proof of greatness
- No achievement listings ("I increased X by Y%") — let the project speak
- If current company is remote with an international team, say so explicitly
- Keep project mentions to one or two max — the most relevant ones only

**Senior/staff variant:** at senior level, credibility comes from scope and shipped systems, not side projects. Lead with the systems owned and the org-level impact, in one factual paragraph — no enthusiasm hedges ("I feel like I'd be a strong fit" reads junior at staff level and is actively wrong here):

```
I'm currently a staff engineer at [Company], where I own the [system] —
[scale: requests/sec, data volume, uptime, or revenue it carries] — and led
the [migration/rearchitecture] that [one-line org-level outcome, e.g., "let
four product teams ship independently"]. Before that I [one line of relevant
scope]. No side projects needed as proof — the systems are the proof.
```

### The Connection (1-2 sentences)
Bridge between their background and the specific role. Should feel like an observation, not a claim.

```
I think you're looking for [what the role actually wants] — that's the kind of
work I've been doing, and it maps directly.
```

Or more specific:
```
My stack maps naturally to yours — [specific tech overlap]. But more than the
stack, it's the [domain/problem] that I'm genuinely interested in.
```

### Portfolio Link
```
More about me: [portfolio URL]
```
One line. No elaboration.

### Closing
End with low-pressure, confident energy. Not desperate, not corporate.

```
I'm [currently at [Company] and] open to what's next. I think we'd both get
something out of a conversation.

[First Name]
[email]
```

**Avoid:**
- "I look forward to hearing from you"
- "Please find attached my resume"
- "I would love the opportunity to..."
- "I am excited to potentially join..."

## Confidential Search (employed candidates — ask first)

Cold emails get forwarded — including, sometimes, to the candidate's current employer. Before drafting:

1. **Ask:** "Are you comfortable naming your current employer in this email?"
2. **If yes:** normal body.
3. **If no:** use the blind variant — describe the employer by type and stage, not name:

```
I'm currently a senior engineer at a Series-B dev-tools company, where I own
the [system/domain] — [scale proof point].
```

A blind variant costs almost nothing with founders and EMs; recruiters may push for the name, which is fine to give later in the process.

**Standing rule:** never reference legal disputes, HR complaints, settlements, or negative reasons for leaving in any outreach — not even euphemistically ("you may have seen the news"). Reason-for-leaving, if asked: one neutral forward-leaning line.

## Recipient-Type Differentiation

**Founder (CEO/CTO at startup):**
- Hook-first; they respond to insight about their market/product, not credentials
- Emphasize scope + velocity ("owned X end to end", "shipped Y in N months")
- Shortest acceptable version; founders skim hardest

**Engineering Manager (EM):**
- Technical insight + the connection; they want to know what it's like to work with you
- Lead with the systems owned and how you work with teams (mentoring, design reviews, incident leadership)
- The role-context subject line matters most here

**In-house recruiter:**
- They triage on: stack, level, location, timeline. Front-load all four in the first two sentences
- Least tolerant of the "interesting observation" opening — get to the profile fast:

```
Hi [Name] — I'm a staff backend engineer ([Go, Kubernetes, AWS]) currently at
[a Series-B fintech / Company], based in [city], open to [remote roles] from
[date]. I saw the [Role] req — my last four years have been [one-line scope].
```

## Research Before Writing

Before writing the email, gather:
1. **Company angle** — read their website, JD, or About page. Find one specific thing worth mentioning.
2. **Recipient name** — LinkedIn, the team page, Wellfound, the company's engineering blog, or their GitHub org (all better than stale directories). "Hi [Name]" beats "Hi Hiring Manager" every time.
3. **Relevant projects/systems** — match the candidate's most relevant work to the role domain.
4. **Stack overlap** — mention it only if there's a genuine match.

If the user provides a JD but no company website, ask for it or fetch it before writing.

## Length Guidelines

- **Ideal:** 200–300 words (recruiter version can be shorter)
- **Maximum:** 400 words
- **Minimum:** 150 words (don't strip out substance for brevity)

Longer is fine if every sentence earns its place. Cut anything that could apply to any company.

## Follow-Up Protocol

Most first emails get no reply — that's the default, not a signal. One polite bump is the difference between a 5% and a 30% response rate; three bumps undoes it.

- **When:** 5-7 business days after the first email
- **Length:** 2-3 sentences, in the same thread
- **Content:** one NEW piece of information (a relevant result, a link, a specific answer to their likely objection) — never "just bumping this"
- **Then: stop.** No third email unless they reply.

```
Hi [Name] — one addition since my note last week: [new piece of info, e.g.
"we just open-sourced the ingestion framework I mentioned — [link]"]. If the
timing's wrong, no worries at all.

[First Name]
```

## Output Format

Always wrap the final email in a plain code block for clean copy-paste:

```
Subject: [chosen subject line]

Hi [Name],

[Email body]

[First Name]
[email]
```

## Common Mistakes to Avoid

**Too confident:** ❌ "I would be an exceptional addition to your team" / "My background uniquely positions me for this role" → ✅ state the facts of what you've owned and let them conclude; at senior level, directness beats both hedges and claims.

**Too humble:** ❌ "I know I may not have all the experience you're looking for, but..." / "I'm just reaching out on the off chance..." → ✅ acknowledge gaps directly and move on — don't apologize.

**Too long:** ❌ three paragraphs listing every achievement → ✅ one paragraph on background, one on the connection.

**Too generic:** ❌ "I am writing to express my interest in..." → ✅ open with what specifically pulled them to this company.

**No research:** ❌ "I love your product and mission" → ✅ "The 5% stat — only 5% of a $25B market online — doesn't feel like a feature gap, it feels like an entire industry that hasn't digitised"

## Examples

Two worked examples live in `references/examples.md`:

1. **Mid-level / international candidate** — hook-first to a founder, location disclosed upfront, side projects as proof.
2. **Senior/staff engineer (domestic, confidential variant)** — engineering-blog hook, systems owned + org impact in one factual paragraph, blind employer ("a Series-B fintech"), leveling addressed head-on. No "I feel like" hedges, no side projects, no achievement list — at staff level the systems are the proof.
