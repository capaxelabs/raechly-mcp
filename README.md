<p align="center"><img src="assets/logo.svg" width="72" alt="Raechly logo"></p>

<h1 align="center">Raechly MCP</h1>

<p align="center">Run cold email from your AI app: mailboxes, warmup, lead search, campaigns, replies and deals.</p>

<p align="center">
  <a href="https://www.raechly.com">Website</a> ·
  <a href="https://www.raechly.com/mcp">Docs</a> ·
  <a href="https://www.raechly.com/pricing">Pricing</a> ·
  <a href="https://registry.modelcontextprotocol.io/v0.1/servers?search=com.raechly">MCP Registry</a>
</p>

<p align="center">
  <a href="https://cursor.com/en/install-mcp?name=raechly&config=eyJ1cmwiOiJodHRwczovL21jcC5yYWVjaGx5LmNvbS9tY3AifQ=="><img src="https://cursor.com/deeplink/mcp-install-dark.svg" alt="Add Raechly to Cursor" height="32"></a>
  <a href="https://vscode.dev/redirect/mcp/install?name=raechly&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.raechly.com%2Fmcp%22%7D"><img src="https://img.shields.io/badge/VS_Code-Install_server-0098FF?style=for-the-badge&logo=visualstudiocode&logoColor=white" alt="Install Raechly in VS Code" height="32"></a>
</p>

Raechly is a hosted MCP server at `https://mcp.raechly.com/mcp`. Connect it to Claude, ChatGPT, Cursor or any MCP client and run outbound by asking: set up sending domains, warm mailboxes, find leads, write the sequence and handle replies.

This repo holds the install files for Claude Code, Codex, Cursor and other clients. The server itself is hosted by Raechly, so there is nothing to run.

## What you can ask

- "Suggest 3 sending domains for my company and set up 2 mailboxes on each with warmup."
- "Find 200 heads of finance at US SaaS companies with 50 to 500 staff and add them to a lead list."
- "Write a 4-step campaign for that list about our invoice automation tool and show me the emails before anything sends."
- "Show today's replies, mark the interested ones and draft answers to their questions."
- "How did last week's campaign do? Open rate, replies and meetings booked."

## Install

### Claude Code

```bash
claude plugin marketplace add capaxelabs/plugins
claude plugin install raechly@capaxe
```

Then run `/mcp` in Claude Code, pick **raechly** and sign in to Raechly.

Prefer a plain MCP server over a plugin:

```bash
claude mcp add --transport http raechly https://mcp.raechly.com/mcp
```

### Claude.ai and Claude Desktop

1. Open **Settings > Connectors** and select **Add custom connector**.
2. Name it **Raechly** and paste `https://mcp.raechly.com/mcp`.
3. Select **Connect** and sign in.

### ChatGPT

1. Open **Settings > Apps & Connectors > Advanced settings** and turn on **Developer mode**.
2. In **Apps & Connectors**, select **Create**.
3. Name it **Raechly**, paste `https://mcp.raechly.com/mcp` and choose **OAuth**.

### Codex

```bash
codex plugin marketplace add capaxelabs/plugins
codex plugin add raechly@capaxe
```

Or add it as a plain MCP server:

```bash
codex mcp add raechly --url https://mcp.raechly.com/mcp
```

### Cursor

Use the **Add to Cursor** button above, or add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "raechly": { "url": "https://mcp.raechly.com/mcp" }
  }
}
```

### VS Code

Use the **Install** button above, or add to `.vscode/mcp.json`:

```json
{
  "servers": {
    "raechly": { "type": "http", "url": "https://mcp.raechly.com/mcp" }
  }
}
```

### Any other MCP client

| Setting | Value |
| --- | --- |
| URL | `https://mcp.raechly.com/mcp` |
| Transport | Streamable HTTP |
| Auth | OAuth, or an org API key as `Authorization: Bearer rk_...` |

Create API keys in the [Raechly dashboard](https://dash.raechly.com/settings) under **Connect to AI**.

## Tools

100+ tools, grouped by what they cover:

| Area | Examples |
| --- | --- |
| Domains and mailboxes | `domain_ideas`, `create_domain`, `check_domain`, `create_mailbox`, `connect_mailbox` |
| Warmup | `start_warmup`, `warmup_stats`, `skip_warmup` |
| Leads and contacts | `run_lead_search`, `search_contact_store`, `create_lead_list`, `import_contacts`, `research_company` |
| Campaigns | `generate_campaign`, `review_campaign_emails`, `send_test_email`, `set_campaign_status`, `get_campaign_stats` |
| Replies | `list_replies`, `suggest_reply_answer`, `reply_to_lead`, `set_reply_outcome` |
| Deals | `create_deal`, `move_deal`, `deals_from_past_replies`, `sdr_report` |
| Journeys | `create_journey_from_recipe`, `enroll_contacts`, `get_journey_stats` |

Tools that send email or change data are marked as such, so your AI app asks before it runs them.

## Links

- Website: https://www.raechly.com
- Docs: https://www.raechly.com/mcp
- Pricing: https://www.raechly.com/pricing
- Privacy: https://www.raechly.com/privacy
- Terms: https://www.raechly.com/terms
- Support: support@raechly.com

## Files in this repo

| File | Read by |
| --- | --- |
| `.claude-plugin/plugin.json`, `.mcp.json` | Claude Code |
| `plugin.json`, `mcp.json` | Codex and other [Agent Plugins](https://agent-plugins.org) clients |
| `.cursor-plugin/plugin.json` | Cursor |
| `server.json` | [Official MCP Registry](https://registry.modelcontextprotocol.io) |
| `glama.json` | [Glama](https://glama.ai/mcp/servers) |

## License

The files in this repo are MIT licensed. Use of the Raechly service is covered by its [terms](https://www.raechly.com/terms).
