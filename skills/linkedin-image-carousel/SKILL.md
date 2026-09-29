---
name: linkedin-image-carousel
description: Plan and write a LinkedIn multi-image post (2–20 images) slide by slide, with the caption, ready to publish with the PostOnce LinkedIn MCP. Use when the user wants a LinkedIn carousel, a list or step-by-step post with images, or to turn a thread, article or guide into swipeable slides on LinkedIn.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# LinkedIn image carousel

LinkedIn multi-image posts show images in a grid that opens into a swipeable viewer. This server publishes them as up to 20 images (JPEG, PNG or GIF, up to 20 MB each). It can't publish LinkedIn document (PDF) carousels; if the user has a PDF, suggest exporting its pages as images.

## Plan the slides

Use 5–8 images for most posts. Write a slide plan before any design:

| Slide | Job | Words |
| --- | --- | --- |
| 1. Cover | The hook: names the reader, a number or the result. Must work alone in the grid. | 12 or fewer |
| 2–N. Body | One point per slide. Numbered if it's a list; numbering continues across slides. | 12–30 each |
| Last | One takeaway or one ask (save, comment, follow). | 15 or fewer |

Rules that hold up across top carousels:
- One idea per slide, large text, the same layout on every slide so it reads as one piece.
- A swipe cue on the cover ("Swipe →") and none on the last slide.
- Real screenshots, numbers or examples beat stock images.
- Keep text inside the middle of each image; the grid preview crops edges. 1080×1350 (4:5) or 1080×1080 works well.

## Caption

Write the caption with the `linkedin-post-writer` rules: the first two lines hook, the body says why the slides matter, and the ending asks one easy question. Don't repeat every slide in the caption.

## Making the images

If the user has a design tool or renderer, give them the slide text and layout notes. If they already have images, check the count (20 max), format and order. Upload each image with `create_upload_url`, then pass the public URLs in slide order as `media` in `create_post` (see the `postonce` skill). Don't mix images and video in one post.

## Output

Return the slide plan (slide number, headline, supporting text, visual note), then the caption. Offer to publish or schedule once the images exist.
