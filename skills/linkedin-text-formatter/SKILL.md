---
name: linkedin-text-formatter
description: Format a LinkedIn post so it's easy to read in the feed: line breaks, bullets, optional Unicode bold and italic, and a check that the hook lands before "see more". Use when the user asks for a LinkedIn text formatter, LinkedIn post formatter, bold or italic text on LinkedIn, or to clean up the formatting of a post before publishing it with the PostOnce LinkedIn MCP.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# LinkedIn text formatter

LinkedIn posts are plain text. There's no bold, italic or bullet button in the post box, and pasted Markdown shows up as literal asterisks. Format with line breaks, simple symbols and, sparingly, Unicode letters. Output the post exactly as it should be published.

## Line breaks and spacing

- One thought per line. A blank line between ideas.
- No paragraph longer than 3 lines on a phone.
- Keep line breaks as real newlines in the post `content`. Don't add HTML or Markdown.

## The "see more" fold

LinkedIn cuts the post after roughly the first two lines (about 210 characters on desktop, often less on mobile, and fewer when the lines are short) and shows "…see more". Check the fold:

- Count the characters and lines before the first cut. Line 1 must carry the hook on its own.
- If the hook needs line 2, keep line 1 short so both fit.
- Don't open with a blank line, a hashtag, an emoji row or a link.
- State where the fold falls in your output.

## Bullets and lists

- Use simple characters: "•", "→", "–" or numbers ("1.", "2."). Stay with one style per post.
- 3–7 items. Each item one line if possible.
- Emoji bullets are fine only if the user's style uses them; never a wall of them.

## Unicode bold and italic

LinkedIn has no native bold, but Unicode "mathematical" letters (𝗯𝗼𝗹𝗱, 𝘪𝘵𝘢𝘭𝘪𝘤) look bold or italic. Use them only when the user asks, and warn them:

- Screen readers read them letter by letter or skip them, so people using assistive tech may not understand the text.
- LinkedIn search and many tools don't match them as normal words.
- They count as characters toward the limit and some older devices show boxes.

If used: at most a few words per post (a section label or one key phrase), never the hook's main words, never whole sentences, never numbers people might search.

## Limits and checks

- Hard limit: 3,000 characters. Text over it is cut off when published, not rejected. Count before publishing.
- 0–3 hashtags, at the end.
- Links in the body tend to reduce reach; suggest the first comment unless the user wants the link in the post. This server can't post the comment for them.
- Keep mentions as plain names; this server doesn't create @mention tags.

## Output

Return the formatted post in a plain code block so line breaks survive copying, then: character count, where the "see more" fold falls, and any Unicode styling used with the accessibility note. Offer to publish or schedule it with the `postonce` skill; confirm the account (profile or which page) and the time before calling `create_post`.
