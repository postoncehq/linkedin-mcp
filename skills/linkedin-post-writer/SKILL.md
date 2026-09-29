---
name: linkedin-post-writer
description: Write LinkedIn posts for a personal profile or company page that people read, react to and comment on. Use when the user asks to write, rewrite, improve or turn something (an update, article, video, idea or notes) into a LinkedIn post, before publishing it with the PostOnce LinkedIn MCP.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# LinkedIn post writer

Write one LinkedIn post that earns attention in the feed, then hand it to the `postonce` skill if the user wants it published or scheduled.

## Before writing

Get or infer: who is posting (a person or a company page), who they want to reach, the one idea the post carries, and any fact, number or story that proves it. If the user gives a long source (article, transcript, notes), pick the single most interesting idea; one post, one idea. Never invent numbers, results, customers or quotes.

## The first two lines decide everything

LinkedIn shows roughly the first two lines before "…see more". Write those lines to make someone tap. Pick one pattern:

| Pattern | Template |
| --- | --- |
| Name the moment | Open on a specific situation the reader lives. "You posted it on Tuesday. It's Friday and it's still not on Instagram." |
| Worst advice | "WORST ADVICE EVER" then the quoted bad advice, then your stance. |
| Contrarian | "[Topic] advice that doesn't work:" · "Doing [common effort] won't [expected result]." |
| Numbered list | "[N] signs it's time to [big decision]." · "[N] harsh truths nobody told you about [topic]:" |
| Mistake | "One of the biggest mistakes I made in my first year of [skill] was [choice]." |
| Comparison | "The difference between [A] and [B]." |
| Proof | "I analyzed my [N]+ [posts / data points]. Here's what actually worked." · "These [N] [templates] helped me get [result]." |

What to avoid, from studying top company and creator posts:
- Opening with a question. Question openers performed worst (about half the reactions of the same account's normal post).
- Opening with the product or "We're excited to announce". Announcements do well only when line 1 is about the reader's problem.
- Generic tips with no stance. Tip posts underperform unless they take a side.

## The body

- Short lines, one thought per line, blank line between ideas. No walls of text.
- Make the stance clear by line 4.
- Specifics beat adjectives: a number, a name, a before/after, a moment.
- Plain words. No "game-changer", "unlock", "in today's fast-paced world", "let's dive in", emoji bullet lists or hashtag walls.
- Length: 600–1,300 characters works for most posts. The hard limit is 3,000.
- A company page can sound human. Named people and real moments beat brand voice.

## The ending

End on one of: a specific question that's easy to answer from experience ("What's the one thing you always change before a video goes somewhere else?"), a clear takeaway line, or a soft next step. One ending only.

## Links, hashtags and media

- Links in the post body tend to reduce reach. Put the link in the first comment, or say "link in the comments", unless the user wants it in the post.
- 0–3 hashtags, at the end, only if they're specific.
- Native media beats text-only and links: a real photo, a simple chart, a two-frame before/after image, or a short video. Suggest one. For several images, use the `linkedin-image-carousel` skill. LinkedIn document (PDF) posts can't be published through this server.

## Output

Give the user the post exactly as it will appear, then one line on the hook pattern used and any suggested visual. Offer to publish or schedule it with the `postonce` skill; confirm the account (profile or which page) and the time before calling `create_post`.
