# Ziply plugin (QA)

The Ziply plugin for Claude and ChatGPT, pointed at the **Ziply QA environment**. It finds what to write from
your Ziply topic queue, writes blog posts, pages, eBooks, social posts and Reddit discussions in
your brand's voice, checks them against Ziply's AI-readiness rules with links to your own pages, and saves them to
Ziply Content Factory as drafts. It also finds and updates the blogs and eBooks already saved
there. It never publishes.

## Install

**Claude desktop app:** Settings → Plugins → Add marketplace → enter
`ZplyAI/ziply-qa-mcp-plugin` → Sync, then install **ziply**.

**Claude Code:**

```bash
claude plugin marketplace add ZplyAI/ziply-qa-mcp-plugin
claude plugin install ziply@ziply-qa
```

**ChatGPT desktop app (Work or Codex):** add `ZplyAI/ziply-qa-mcp-plugin` as a plugin marketplace,
then install **Ziply QA**.

Then connect Ziply when asked (in Claude Code: `/mcp` → `ziply` → Authenticate) and sign in with
your Ziply account. Ask "Is Ziply connected?" to check.

## What's inside

```
CAPABILITIES.md                    what the plugin can do, for customers
.claude-plugin/marketplace.json    lists the plugin, so this repo can be added as a marketplace
.agents/plugins/marketplace.json   the same, for ChatGPT
plugins/ziply/
├── .claude-plugin/plugin.json     plugin name, version and description
├── .mcp.json                      the Ziply connection (MCP server URL)
├── plugin.json, mcp.json          the same, for ChatGPT
├── assets/icon.png                ChatGPT icon
├── skills/                        9 skills: setup, find topics, brief, long-form, readiness check, refresh, social, Reddit, save
│                                  (long-form and social carry Ziply's method and templates in references/)
└── commands/                      /ziply:status, topics, brief, write, check, refresh, social, reddit, push
```

See [CAPABILITIES.md](CAPABILITIES.md) for everything the plugin can do, what it needs, and what's not
in this release.
