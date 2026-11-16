<p align="center"><img src=".github/cover.png" alt="LinkedIn MCP server for Claude, ChatGPT, Cursor and Codex" width="100%"></p>

# LinkedIn MCP Server

LinkedIn MCP server for Claude, ChatGPT, Cursor and Codex. Your AI agent can write, publish and schedule LinkedIn posts on your profile or company page through LinkedIn's official API. There's no scraping, no browser automation and no LinkedIn developer app to set up.

It runs on [PostOnce](https://postonce.to?utm_source=github&utm_campaign=linkedin-mcp)'s hosted MCP server and comes with LinkedIn writing skills, so your agent knows what a good LinkedIn post looks like before it posts one.

**[Start free for 7 days, no card →](https://postonce.to?utm_source=github&utm_campaign=linkedin-mcp)** · Used by 3,500+ users

[![Claude](https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logoColor=white&logo=claude)](https://postonce.to/integrations/claude?utm_source=github&utm_campaign=linkedin-mcp) [![ChatGPT](https://img.shields.io/badge/ChatGPT-10A37F?style=for-the-badge&logoColor=white)](https://postonce.to/integrations/chatgpt?utm_source=github&utm_campaign=linkedin-mcp) [![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=for-the-badge&logoColor=white&logo=claude)](https://postonce.to/integrations/claude-code?utm_source=github&utm_campaign=linkedin-mcp) [![Codex](https://img.shields.io/badge/Codex-000000?style=for-the-badge&logoColor=white)](https://postonce.to/integrations/codex?utm_source=github&utm_campaign=linkedin-mcp) [![Cursor](https://img.shields.io/badge/Cursor-000000?style=for-the-badge&logoColor=white&logo=cursor)](https://postonce.to/integrations/cursor?utm_source=github&utm_campaign=linkedin-mcp) [![Gemini CLI](https://img.shields.io/badge/Gemini_CLI-8E75B2?style=for-the-badge&logoColor=white&logo=googlegemini)](https://postonce.to/integrations/gemini?utm_source=github&utm_campaign=linkedin-mcp) [![Grok](https://img.shields.io/badge/Grok-000000?style=for-the-badge&logoColor=white&logo=x)](https://postonce.to/integrations/grok?utm_source=github&utm_campaign=linkedin-mcp) [![n8n](https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logoColor=white&logo=n8n)](https://postonce.to/integrations/n8n?utm_source=github&utm_campaign=linkedin-mcp) [![Make](https://img.shields.io/badge/Make-6D00CC?style=for-the-badge&logoColor=white&logo=make)](https://postonce.to/integrations/make?utm_source=github&utm_campaign=linkedin-mcp) [![Zapier](https://img.shields.io/badge/Zapier-FF4F00?style=for-the-badge&logoColor=white&logo=zapier)](https://postonce.to/integrations/zapier?utm_source=github&utm_campaign=linkedin-mcp) [![Any MCP client](https://img.shields.io/badge/Any_MCP_client-1D4ED8?style=for-the-badge&logoColor=white)](https://postonce.to/integrations/mcp?utm_source=github&utm_campaign=linkedin-mcp)

```
You:    Turn this week's product update into a LinkedIn post for our company page
        and schedule it for Tuesday 9am.
Claude: Drafted it with the linkedin-post-writer skill. Here's the post; the
        first line names the problem, the link goes in the first comment.
        Scheduled on PostOnce for Tue 9:00 on "Acme" (company page).
```

Full setup guide with examples: [postonce.to/mcp/linkedin](https://postonce.to/mcp/linkedin?utm_source=github&utm_campaign=linkedin-mcp)

## What hosted PostOnce handles for you

| | |
| --- | --- |
| Approved platform apps | No developer app or platform review on your side. Connect your accounts and post. |
| Official APIs | Every post goes through each platform's official API. No scraping, no browser automation. |
| Retries | Temporary platform errors retry on their own, without posting twice. |
| Status per platform | Each post shows its status and live link on every platform. |

## What you can do

| Ask your agent to | How it works |
| --- | --- |
| Publish a text post now | `create_post` on your connected LinkedIn account |
| Schedule a post for later | `create_post` with `publish_at` |
| Post images (up to 20) or one video (up to 30 minutes) | `create_upload_url`, upload, then `create_post` with `media` |
| Post to your profile, or to a company page you admin | Pick the account from `list_accounts`. Company pages are connected from the PostOnce dashboard |
| Save a draft to finish later | `create_draft` |
| Check whether a post went out, and get its URL | `get_post` |
| Change or cancel a scheduled post | `update_post`, `cancel_post` |
| Post the same thing to LinkedIn and other platforms | Add more targets to `create_post` (Instagram, TikTok, YouTube, X, Threads, Facebook, Pinterest, Bluesky) |

Not supported: reading your feed, searching people, sending messages or connection requests, and LinkedIn document (PDF) posts. This server publishes; it doesn't browse LinkedIn for you.

## Setup (about a minute)

You need a [PostOnce account](https://postonce.to?utm_source=github&utm_campaign=linkedin-mcp) (free for 7 days, no card) with your LinkedIn profile or page connected.

**Claude (claude.ai and desktop) and ChatGPT:** add a custom connector with the URL below and sign in with PostOnce. No API key.

```
https://postonce.to/mcp
```

Step-by-step: [Claude](https://postonce.to/integrations/claude?utm_source=github&utm_campaign=linkedin-mcp) · [ChatGPT](https://postonce.to/integrations/chatgpt?utm_source=github&utm_campaign=linkedin-mcp)

**Claude Code:** install the plugin. It adds the MCP connection and the skills together, and the first time it connects your browser opens to sign in with PostOnce. No API key.

**Cursor:** install the plugin, then click **Connect** next to `postonce` in Cursor's MCP settings and sign in with PostOnce. No API key.

**Codex:** install the plugin, then run `codex mcp login postonce` and sign in with PostOnce in the browser. No API key.

```bash
# Claude Code
claude plugin marketplace add postoncehq/plugins
claude plugin install linkedin-mcp@postoncehq
```

Step-by-step: [Claude Code](https://postonce.to/integrations/claude-code?utm_source=github&utm_campaign=linkedin-mcp) · [Codex](https://postonce.to/integrations/codex?utm_source=github&utm_campaign=linkedin-mcp) · [Cursor](https://postonce.to/integrations/cursor?utm_source=github&utm_campaign=linkedin-mcp)

**Any other MCP client:** point it at `https://postonce.to/mcp` (Streamable HTTP) and sign in with PostOnce when it asks. Clients without OAuth can send the header `Authorization: Bearer <your PostOnce API key>` instead (API keys are in [PostOnce preferences](https://postonce.to/dashboard/preferences?utm_source=github&utm_campaign=linkedin-mcp) and need a paid plan).

## Skills included

| Skill | What it does |
| --- | --- |
| [`linkedin-post-writer`](skills/linkedin-post-writer/SKILL.md) | Writes LinkedIn posts that get read: a first line that stops the scroll, short lines, one idea, a real ending. Uses hook patterns taken from high-performing LinkedIn posts. |
| [`linkedin-image-carousel`](skills/linkedin-image-carousel/SKILL.md) | Plans a multi-image post (up to 20 images) slide by slide, with the caption to go with it. |
| [`linkedin-text-formatter`](skills/linkedin-text-formatter/SKILL.md) | Formats a post for the feed: line breaks, bullets, optional Unicode bold and italic (with the accessibility caveat), and a check that the hook lands before "see more". Stays under the 3,000-character limit. |
| [`linkedin-headline-generator`](skills/linkedin-headline-generator/SKILL.md) | Writes profile headline options up to 220 characters, built on role, outcome and search keywords. You paste the one you pick into LinkedIn. |
| [`linkedin-profile-optimizer`](skills/linkedin-profile-optimizer/SKILL.md) | Rewrites your About section, Featured items, banner copy and experience bullets. You paste them into your profile. |
| [`linkedin-content-calendar`](skills/linkedin-content-calendar/SKILL.md) | Plans 1–4 weeks of posts from your goals or a source like a blog post or transcript, drafts each one and schedules them on approval. |
| [`postonce`](skills/postonce/SKILL.md) | Publishing workflow: pick the right account, upload media, schedule, and confirm the post actually went live. |

## FAQ

**Does LinkedIn have an official MCP server?**
Not for posting. As of November 2026, LinkedIn's only official connector is LinkedIn Hiring Pro, which posts job listings from Claude. With this server, PostOnce publishes regular LinkedIn posts through LinkedIn's official posting API.

**Is it safe for my LinkedIn account?**
Yes. Posts go through LinkedIn's official posting API with the permissions you grant when you connect. There's no scraping and no browser session, and you can revoke access any time.

**Can Claude post to LinkedIn?**
Yes, once it's connected to an MCP server that can publish, like this one. Claude writes the post, then calls `create_post`.

**Can it post to a LinkedIn company page?**
Yes, to pages you're an admin of. Connect the page from the [PostOnce dashboard](https://postonce.to/dashboard/accounts?utm_source=github&utm_campaign=linkedin-mcp); connecting from your agent links your personal profile only. Once the page is connected, your agent can post to it.

**Do I need a LinkedIn developer app or API approval?**
No. PostOnce holds the LinkedIn API access; you just connect your account.

**Is it free?**
The skills and this repo are free and MIT-licensed. Publishing runs through a PostOnce account, which you can try free for 7 days without entering a card. After that, see [pricing](https://postonce.to/pricing?utm_source=github&utm_campaign=linkedin-mcp).

## Data and privacy

- The posts, captions and media you ask your agent to publish are sent to PostOnce and on to the platforms you choose. Nothing is published without a request from you.
- Media files you upload go straight to PostOnce's file storage through a short-lived signed upload link, then publish from there. Uploaded media is publicly reachable so the platforms can fetch it.
- PostOnce stores your posts, media and connected account names so it can schedule them and show your publishing history. You can disconnect accounts and revoke access at any time in [PostOnce preferences](https://postonce.to/dashboard/preferences?utm_source=github&utm_campaign=linkedin-mcp).
- The skills themselves run in your agent and send nothing anywhere else.

Full details: [privacy policy](https://postonce.to/privacy-policy?utm_source=github&utm_campaign=linkedin-mcp) · [terms](https://postonce.to/tos?utm_source=github&utm_campaign=linkedin-mcp).

## Other platforms

The same connection posts everywhere PostOnce supports. Platform repos with their own skills:
[Instagram MCP](https://github.com/postoncehq/instagram-mcp) · [TikTok MCP](https://github.com/postoncehq/tiktok-mcp) · [YouTube MCP](https://github.com/postoncehq/youtube-mcp) · [Facebook MCP](https://github.com/postoncehq/facebook-mcp) · [X (Twitter) MCP](https://github.com/postoncehq/x-mcp) · [Threads MCP](https://github.com/postoncehq/threads-mcp) · [Bluesky MCP](https://github.com/postoncehq/bluesky-mcp) · [Pinterest MCP](https://github.com/postoncehq/pinterest-mcp)

## License

MIT. See [LICENSE](LICENSE).
