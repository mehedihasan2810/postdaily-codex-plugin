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
- **Nothing publishes immediately without your yes**: PostDaily refuses to
  publish now unless you confirmed the exact text and channels, and the tools
  that publish, cancel or delete are marked as such. Codex asks before tool
  calls according to your Codex approval settings; to have it ask before every
  PostDaily call, add this to `~/.codex/config.toml`:

  ```toml
  [plugins."postdaily".mcp_servers.postdaily]
  default_tools_approval_mode = "prompt"
  ```

## Development

This repository is a Codex plugin marketplace
(`.agents/plugins/marketplace.json`) with one plugin,
[`plugins/postdaily`](./plugins/postdaily). The same plugin is the package
submitted to OpenAI's plugin directory, which serves ChatGPT and Codex, so its
manifest also carries the directory listing and review cases. It
is published from PostDaily's main codebase, where the plugin is kept in step
with the MCP server it wraps and checked against the directory's rules. To try
an install without touching your own Codex setup, point `CODEX_HOME` at an
empty directory first.

## Help

- [Connecting AI apps to PostDaily](https://www.postdaily.app/help/connect-ai-apps)
- support@postdaily.app

## License

[MIT](./LICENSE)
