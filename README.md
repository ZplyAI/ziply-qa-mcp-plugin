# Ziply plugin (QA)

The Ziply plugin for Claude, pointed at the **Ziply QA environment**. It finds what to write from
your Ziply topic queue, writes blog posts, pages, eBooks, social posts and Reddit discussions in
your brand's voice, and saves them to Ziply Content Factory as drafts. It never publishes.

## Install

**Claude desktop app:** Settings → Plugins → Add marketplace → enter
`ZplyAI/ziply-qa-mcp-plugin` → Sync, then install **ziply**.

**Claude Code:**

```bash
claude plugin marketplace add ZplyAI/ziply-qa-mcp-plugin
claude plugin install ziply@ziply-qa
```

Then connect Ziply when asked (in Claude Code: `/mcp` → `ziply` → Authenticate) and sign in with
your Ziply account. Ask "Is Ziply connected?" to check.

## What's inside

```
.claude-plugin/marketplace.json    lists the plugin, so this repo can be added as a marketplace
.agents/plugins/marketplace.json   the same, for ChatGPT
plugins/ziply/
├── .claude-plugin/plugin.json     plugin name, version and description
├── .mcp.json                      the Ziply connection (MCP server URL)
├── plugin.json, mcp.json          the same, for ChatGPT
├── assets/icon.png                ChatGPT icon
├── skills/                        7 skills: setup, find topics, brief, long-form, social, Reddit, save
└── commands/                      /ziply:status, topics, brief, social, reddit, push
```

Not in this release: AI-readiness checks, updating saved drafts, and Ziply's content library.
