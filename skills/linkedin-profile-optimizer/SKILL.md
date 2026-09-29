---
name: linkedin-profile-optimizer
description: Rewrite the parts of a LinkedIn profile that decide whether people follow, hire or reply: About section, Featured items, banner copy and experience bullets. Use when the user asks for LinkedIn profile optimization, a LinkedIn summary or About section, a summary generator, experience bullets, banner text, or a LinkedIn profile review.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# LinkedIn profile optimizer

People check a profile after they see a post or a comment. The profile should tell them in seconds who this person helps and why to follow or reach out. Write the copy; the user pastes it into LinkedIn themselves. This server publishes posts; it can't read or edit profiles.

## Inputs to get first

- The goal: get hired (which role), win clients, build an audience, raise money, or hire.
- The audience and the keywords they'd search.
- Current profile text (ask the user to paste headline, About and recent roles).
- Real proof: results, clients, projects, credentials, links to show off.

Never invent employers, dates, numbers or credentials.

## Headline

Use the `linkedin-headline-generator` skill (220 characters max).

## About section (up to 2,600 characters)

- LinkedIn shows the first few lines before "see more", so open with who you help and what you do, not "I'm a passionate…".
- Structure: what you do and for whom (2–3 lines), how you do it or what makes it different, 3–5 proof points, a clear next step ("Email me at…", "DM me about…", "Book a call: link").
- Short paragraphs, first person, plain words. Include the keywords naturally.
- Bullets with "•" are fine. Skip Unicode bold here; screen readers and LinkedIn search handle it poorly.

## Featured section

Suggest 3–5 items in priority order: the best post (the user can publish one with `linkedin-post-writer`), a case study or portfolio link, a lead magnet or booking link, a talk or press mention. Give each a short title and a one-line description.

## Banner copy

- LinkedIn's recommended banner size is 1584×396 px. Keep text on the right two-thirds; the profile photo covers the lower left, and mobile crops the edges.
- One line: what you do for whom, or a clear offer. Optional second line: proof or a URL.
- If the environment can render HTML to PNG (for example headless Chrome or Playwright), build it as a 1584×396 HTML page and screenshot it. Otherwise give text and layout notes for a design tool.

## Experience bullets

- 3–5 bullets per role, newest roles in most detail.
- Pattern: action verb, what you did, result or scope. For example: "Rebuilt onboarding emails; trial-to-paid rose from [X] to [Y]." Only real numbers; otherwise describe scope (team size, budget, markets).
- One line of context under the title for small or unknown companies.

## Output

Return each section ready to paste, with character counts for the headline and About section. List what to change first. Tell the user to paste each section into their LinkedIn profile. Offer to write a post that sends people to the updated profile, which can be published with the `postonce` skill.
