# OMNIFAMOUS SEO plugin for Grok Build

Live SEO and AI-visibility data inside Grok Build, served by the OMNIFAMOUS
hosted MCP server. Keyword metrics, backlinks, traffic estimates, competitor
content gaps, technical audits, and whether AI answer engines mention a brand.

Homepage: https://omnifamous.com/seo-mcp

## What this plugin ships

- One skill, `skills/omnifamous-seo/SKILL.md`, describing when to use the tools.
- One MCP server config, `.mcp.json`, pointing at our hosted endpoint.

It ships no hooks, no commands, no agents, no scripts, and no binaries. Nothing
in this repo executes on your machine: installing it registers a remote MCP
server and a markdown skill, nothing more.

## Network endpoints

This plugin causes Grok Build to talk to exactly one host:

| Endpoint | Transport | Purpose |
|---|---|---|
| `https://mcp.omnifamous.com/mcp` | Streamable HTTP (MCP, protocol 2025-06-18) | Every tool call |

No other host is contacted, and the plugin itself makes no network calls at
install time.

## Credentials

The free tools (`seo_inspect_url`, `seo_check_robots_sitemap`) need no
credential at all.

The rest need an agent key, sent by the MCP client as
`Authorization: Bearer br_agt_live_...`. A user creates one at
https://omnifamous.com/seo-mcp and it arrives with a free starting balance.

The plugin never reads your environment, your shell profile, your SSH keys or
any dotfile. The key is held by your MCP client, not by anything in this repo.

## Cost

Two tools are free. The rest are metered per successful call, and the exact
price of each is published in its tool description, which `tools/list` returns
before anything is called. A refused call is never charged and answers with the
price and the next step.

## Tools

| Tool | Access |
|---|---|
| `seo_inspect_url` | Free |
| `seo_check_robots_sitemap` | Free |
| `seo_find_broken_links` | Registered |
| `seo_get_audit` | Registered |
| `seo_keyword_ideas` | Metered |
| `seo_traffic_estimate` | Metered |
| `seo_backlinks` | Metered |
| `seo_competitor_gap` | Metered |
| `ai_visibility_check` | Metered |
| `seo_run_audit` | Metered |

The server is the contract. Call `tools/list` for the live surface and the exact
argument schemas.

## Install

Via the xAI plugin marketplace in Grok Build, or point any MCP client at
`https://mcp.omnifamous.com/mcp` directly.

## License

MIT. See [LICENSE](LICENSE).
