# Interview Question Banks

Use with interview-prep-generator. Map each question to a STAR story from the user's story bank; never let an answer introduce claims the user hasn't confirmed.

## Behavioral Questions by Competency

**Leadership:**
- "Tell me about a time you led a team."
- "Describe a situation where you had to make an unpopular decision."
- "How have you developed team members?"
- "Tell me about a time you dealt with a difficult team member."

**Problem-Solving:**
- "Describe a complex problem you solved."
- "Tell me about a time something didn't go as planned."
- "How do you approach problems with incomplete information?"
- "Give an example of an innovative solution you developed."

**Collaboration:**
- "Tell me about working with someone difficult."
- "Describe a time you had to influence someone without authority."
- "How do you handle disagreements with colleagues?"
- "Tell me about a successful cross-functional project."

**Achievement:**
- "What's your proudest professional accomplishment?"
- "Tell me about a time you exceeded expectations."
- "What's the biggest impact you've had in your career?"

**Failure/Growth:**
- "Tell me about a time you failed."
- "What's the biggest mistake you've made at work?"
- "How do you handle criticism?"
- "What would you do differently in your career?" — answer with a professional choice (a technology bet, a scope decision), never a person, employer, or conflict.

## Staff/Senior SWE Question Bank

### System Design (the decisive loop)
- "Design a rate limiter for a multi-tenant API." / "Design a URL shortener at 100K req/s." / "Design metrics ingestion for 1M hosts."
- Staff-level evaluation is about tradeoff articulation and driving the scope: clarify requirements FIRST (scale, consistency, latency budget), state tradeoffs out loud, check in with the interviewer ("should I optimize for write throughput or read latency here?"), and proactively raise operational concerns (deployment, failure modes, cost).
- Expect follow-ups: "how does this fail?", "what's the p99 story?", "how would you migrate to this without downtime?"

### Org-Influence Probes
- "Tell me about changing a technical decision you didn't control."
- "How do you get four teams to adopt a standard none of them asked for?"
- "Tell me about a time you disagreed with a principal/director engineer. How was it resolved?" (Answer shows you can lose well AND hold a position — both are required.)
- "What's the largest technical decision you've driven end to end?"

### Killing Your Own Project
- "Tell me about a time you shut down something you'd championed."
- The strong answer includes the signal that triggered the kill decision, and that YOU made the call before someone else had to.

### Build vs. Buy vs. Deprecate
- "How do you decide whether to build, buy, or keep maintaining an in-house system?"
- "Tell me about a system you deprecated. What did migration look like?"
- Look for: total cost of ownership framing, migration sequencing, sunk-cost resistance.

### Incident & Operations Leadership
- "Walk me through the worst incident you've commanded."
- "How do you run a postmortem that doesn't turn into blame?" 

### Technical Strategy
- "What's a technology bet you made early that paid off — or didn't?"
- "How do you think about platform vs. product investment?"

## Role-Specific Questions

**Product Management:**
- "How do you prioritize features?"
- "Walk me through how you'd approach [product problem]."
- "How do you measure product success?"
- "Tell me about a product you shipped from 0 to 1."

**Engineering (mid-level):**
- "Describe your experience with [specific technology]."
- "How do you approach code reviews?"
- "Tell me about a technical challenge you solved."
- "How do you balance technical debt vs. features?"

**Marketing:**
- "How do you measure campaign success?"
- "Tell me about a campaign that didn't work."

**Sales:**
- "Walk me through your sales process."
- "Tell me about a deal you lost and why."

## Standard Questions

**About You:**
- "Tell me about yourself." (2 min pitch — scope-framed, no cumulative-years)
- "Walk me through your resume." (cap: last 10-15 years, then "earlier roles in X/Y")
- "Why are you looking for a new role?" (neutral departure narrative)
- "Where do you see yourself in 5 years?"

**About the Role:**
- "Why this role?" / "What do you think this role entails?" / "What would you do in your first 90 days?"

**About the Company:**
- "Why this company?" / "What do you know about us?"

## Questions to Ask Interviewers

**For Hiring Manager:**
- "What does success look like in this role at 30/60/90 days?"
- "How is performance measured?"
- "What happened to the last person in this role?"

**For Team Members:**
- "What's a typical day/week like?"
- "What would you want a new hire to know?"
- "How do architecture decisions get made in practice?"

**For Executives:**
- "What's the company's strategy for the next year?"
- "How does this team contribute to company goals?"

**Staff-appropriate:**
- "Who signs off on architecture decisions, and what happens when two staff engineers disagree?"
- "What did the last big technical bet get wrong, and what did it cost?"
- "What's a system you'd deprecate tomorrow if you could, and why can't you?"

**Avoid:**
- ❌ Anything answerable by their website
- ❌ Yes/no questions (ask open-ended)
- ❌ Negative framing of company problems (ask neutrally: "what's the hardest part of operating this system?")
