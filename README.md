# PostDaily for Codex and ChatGPT

Draft, schedule and publish social media posts from Codex or ChatGPT with
[PostDaily](https://www.postdaily.app) — Instagram, Facebook, TikTok, YouTube,
X, Threads, Pinterest, Bluesky and Mastodon (LinkedIn is waiting for
LinkedIn's approval).

You need a PostDaily account — every plan includes AI agent access.

## Install

```bash
codex plugin marketplace add mehedihasan2810/postdaily-codex-plugin
codex plugin add postdaily@postdaily
codex mcp login postdaily
```

The login opens PostDaily in your browser: pick the workspaces Codex may use
and what it can do (Full access, Drafts only or Read only). Change or revoke
it any time in PostDaily under **Settings → AI agents**.

## What you get

- **PostDaily's MCP server** (`https://mcp.postdaily.app/mcp`): up to 20 tools
  for channels, posts, the queue, media and analytics, plus prompts such as
  planning a week of posts.
- **Skills**: `posting` (drafts by default, one text per network, validation,
  a clear yes before publishing now), `local-media` (upload an image, video
  or PDF from your device — with `curl` where there is a terminal, through a
  PostDaily upload page where there is not) and `release-posts` (turn release
  notes or a repository's recent changes into per-network drafts).
- **Approval on every call that can publish or remove**: Codex asks before
  `create_post`, `schedule_post`, `retry_post`, `cancel_post`, `delete_post`
  and `bulk_create_posts`. Reads, edits to drafts and uploads follow your usual
  Codex approval settings.

## Development

This repository is a Codex plugin marketplace
(`.agents/plugins/marketplace.json`) with one plugin,
[`plugins/postdaily`](./plugins/postdaily). The same plugin is the package
submitted to OpenAI's plugin directory, which serves ChatGPT and Codex, so its
manifest also carries the directory listing, screenshots and review cases. It
is published from PostDaily's main codebase, where the plugin is kept in step
with the MCP server it wraps and checked against the directory's rules. To try
an install without touching your own Codex setup, point `CODEX_HOME` at an
empty directory first.

## Help

- [Connecting AI apps to PostDaily](https://www.postdaily.app/help/connect-ai-apps)
- support@postdaily.app

## License

[MIT](./LICENSE)
