---
name: linkedin-headline-generator
description: Write LinkedIn profile headline options (up to 220 characters) built on role, outcome and the keywords people search for. Use when the user asks for a LinkedIn headline, LinkedIn headline generator, headline ideas, or to rewrite or improve their LinkedIn headline.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# LinkedIn headline generator

The headline is the line under your name. It shows next to every post, comment and search result, so it's the most-read line on a profile. Write several options; the user picks one and pastes it into LinkedIn themselves. This server publishes posts; it can't edit profiles.

## Inputs to get first

- Current role and company, or what the user does if they're independent.
- Who they want to notice them: recruiters, clients, investors, peers.
- The result they deliver, with any real proof (a number, a known client, a credential).
- 2–4 keywords people would search to find them ("B2B SaaS marketing", "React developer", "fractional CFO").
- Their current headline, if they want it improved.

Never invent titles, employers, numbers or credentials.

## Rules

- Hard limit: 220 characters. Aim to put the key words in the first 60–70; many places (search results, comments, mobile) show a shortened version.
- Lead with what people search for: the role or the specialty, not a slogan.
- Say who you help and with what, in plain words.
- Proof beats adjectives. "Grew organic signups 3x at Acme" only if true; otherwise a credential or focus area.
- Separate parts with " | " or " · ". Two to four parts is plenty.
- Skip empty words: "passionate", "guru", "ninja", "rockstar", "results-driven", "aspiring".
- Job seekers: include the target role; "Open to work" belongs in LinkedIn's own setting, not the headline.

## Formulas

| Formula | Example |
| --- | --- |
| Role + specialty + audience | Product Designer · B2B SaaS onboarding · Helping teams cut setup time |
| Role at company + proof | Head of Growth at Acme · Built the self-serve funnel from 0 to 10k users |
| Outcome for audience + how | I help clinics fill their calendar with Google Ads · Former agency lead |
| Keyword stack | Data Engineer | Python · dbt · Snowflake | Analytics pipelines for fintech |
| Founder | Founder, Acme (payroll for small restaurants) · Ex-Square |

(Examples are templates; fill them only with the user's real facts.)

## Output

Return 5–7 headline options, each with its character count and one line on who it's for. Mark your top pick and why. Tell the user to paste it into LinkedIn (profile, then the pencil icon next to their name). If they're updating their profile, offer the `linkedin-profile-optimizer` skill, and offer to write a post announcing a new role with the `linkedin-post-writer` skill, which can be published with the `postonce` skill.
