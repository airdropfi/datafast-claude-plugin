# DataFast plugins for Claude Code

> DataFast is revenue-first web analytics: it shows which traffic sources, campaigns and pages bring paying customers, and an AI assistant can read those numbers for you over MCP. Read-only access you approve and can revoke.

## DataFast at a glance

- **What it is:** DataFast is revenue-first web analytics: it shows which traffic sources, campaigns and pages bring paying customers, and an AI assistant can read those numbers for you over MCP. Read-only access you approve and can revoke.
- **Primary user:** An AI assistant (ChatGPT, Claude, Cursor, Gemini CLI or any MCP client) reads the analytics. A human, the site owner, installs the tracking script, approves the connection, reviews the answers and can revoke access.
- **Who pays for it:** Founders, indie hackers and small SaaS or e-commerce teams who want to know which marketing channel produces revenue, not only visits.
- **What it does not do:** The MCP server is read-only: it cannot create sites, change settings, delete data or send revenue events. It returns aggregated numbers, never visitor-level records. Revenue only appears if the owner has connected Stripe or LemonSqueezy or sends payments to the revenue API.
- **Price:** Free plan: $0, 5,000 events a month, 1 website, 7 days of data. Founder: $5 a month, 10,000 events a month, 1 website, 3 years of data, revenue per source and campaign. MCP access has no separate charge. Current plans: https://datafast.app/pricing
- **Integrations:** One-line tracking script, Stripe Connect, LemonSqueezy webhook, a revenue API for any payment provider, and the hosted MCP server at https://datafast.app/api/mcp.
- **Security and data:** OAuth 2.1 with PKCE; you sign in on datafast.app and press Allow. The access token is read-only, stored only as a hash, expires after 90 days and can be revoked by the owner. Tool results contain only the signed-in user's own aggregated analytics.
- **Start in minutes:** Create an account, add the tracking script to your site, wait for traffic, then connect an assistant at https://datafast.app/mcp.
- **MCP:** https://datafast.app/api/mcp (Streamable HTTP, OAuth). Official MCP Registry name: app.datafast/datafast.

## Connect in 60 seconds

```text
/plugin marketplace add airdropfi/datafast-claude-plugin
/plugin install datafast@datafast-plugins
/reload-plugins
```

Then open `/mcp`, choose `datafast`, select Authenticate, sign in to DataFast and press Allow. You need a DataFast account with the tracking script on your site.

## Example prompts

You tag the question; the assistant calls the read-only tools; you review the answer.

- `Which traffic sources brought the most revenue on my DataFast site in the last 30 days?`
- `How many visitors and pageviews did my site get last week, and which day was busiest?`
- `Which UTM campaigns brought visitors this month, and did any of them bring revenue?`
- `Which pages get the most views, and which countries do the visitors come from?`

## Human oversight: what you can see, approve and revoke

- **Approve or refuse a connection.** The consent screen on datafast.app shows the signed-in account, names the connecting client and lists what the assistant will be able to read, with Allow and Cancel.
- **Revoke access.** The Sites page in DataFast lists connected AI assistants with a Revoke button. Revoking deletes the token, so the next call returns 401. Connections also expire after 90 days.
- **Nothing can be changed.** All seven tools are annotated read-only and not destructive. The token cannot create, edit or delete sites, settings or data and cannot see API keys, passwords or payment details.
- **Nothing about your chats is kept.** DataFast stores the connection's name, creation time, last use and expiry, not prompts, answers or tool arguments and results.
- **Usage is bounded.** Each connection is limited to 120 calls a minute and 2,000 a day.

## Links

- Product: https://datafast.app
- MCP page with the agent quickstart (markdown: https://datafast.app/mcp.md): https://datafast.app/mcp
- Pricing: https://datafast.app/pricing
- Official MCP Registry name: `app.datafast/datafast`
- MCP server card: https://datafast.app/.well-known/mcp/server-card.json
- llms.txt: https://datafast.app/llms.txt
- Problems and solutions: https://datafast.app/solutions
- Other ways in: [Cursor kit](https://github.com/airdropfi/datafast-cursor-kit), [Gemini CLI extension](https://github.com/airdropfi/datafast-gemini-extension)

## Details

A Claude Code plugin marketplace with one plugin, [`datafast`](plugins/datafast/README.md).

## Layout

```text
.claude-plugin/marketplace.json     marketplace datafast-plugins
plugins/datafast/                   the plugin: manifest, .mcp.json, commands, skills
scripts/validate.mjs                offline validator (node scripts/validate.mjs)
```

## License

MIT, see `LICENSE`.
