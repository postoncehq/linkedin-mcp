---
name: linkedin-content-calendar
description: Plan 1–4 weeks of LinkedIn posts for a personal profile or company page from the user's goals, content pillars or a source to repurpose (blog URL, video, transcript, newsletter), draft every post, and schedule them with the PostOnce LinkedIn MCP. Use when the user asks for a LinkedIn content calendar, a LinkedIn posting schedule, LinkedIn post ideas for the month, or a plan to post on LinkedIn consistently.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# LinkedIn content calendar

Plan a realistic run of LinkedIn posts, draft each one fully, and schedule the set once the user approves it. Consistency matters more than volume; a plan the user can keep beats a daily plan they drop in week two.

## Inputs to get first

- Who posts: the user's profile, a company page, or both. (Company pages must already be connected in the PostOnce dashboard.)
- Goal: hiring, leads, audience, a launch, thought leadership.
- 2–4 pillars, or a source to repurpose: blog URLs, a video or podcast transcript, a newsletter, release notes.
- How many weeks (1–4) and posts per week. 2–3 a week is a solid default for most people.
- Timezone and preferred days and times. If they have none, suggest weekday mornings in their audience's timezone as a starting point, and say so.
- Real stories, numbers and media they can use. Never invent them.

## Post types to mix

| Type | Media | Notes |
| --- | --- | --- |
| Text post | None | Story, lesson, opinion. Use `linkedin-post-writer`. |
| Image post | 1 image | A real photo, chart or screenshot. |
| Multi-image post | 2–20 images | Lists and step-by-steps. Use `linkedin-image-carousel`. |
| Video | 1 video, up to 30 minutes | Short clips work best for most posts. |

Not possible through this server: document (PDF) posts, polls, articles, newsletters and first comments. If the plan needs a link in the first comment, note it for the user to add after the post goes live.

## Rules

- One idea per post. A long source becomes several posts, each with its own angle.
- Rotate pillars and formats so no two neighboring posts feel the same.
- Each draft follows the `linkedin-post-writer` rules: hook in the first two lines, short lines, one ending. Check the "see more" fold with `linkedin-text-formatter`.
- Keep every post under 3,000 characters; longer text is cut off.
- Don't schedule the same text to the profile and the company page at the same time; rewrite it for each voice.

## Build the calendar

For each slot: date and time, account, pillar, format, hook (line 1), media needed. Flag slots that still need an image or video from the user.

## Output

Return the calendar table, then the full text of every post. Ask for approval and edits. On approval, upload any media with `create_upload_url`, then call `create_post` with `publish_at` for each slot, or `create_draft` for slots still missing media. Confirm the account (profile or which page) and timezone before the first `create_post` (see the `postonce` skill), then report each post ID and scheduled time.
