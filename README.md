# OMNIFAMOUS plugin marketplace

SEO and AI-visibility plugins for Grok Build and Claude Code.

## Install

**Grok Build**

```bash
grok plugin marketplace add omnifamous/marketplace
grok plugin install omnifamous-seo
```

**Claude Code**

```
/plugin marketplace add omnifamous/marketplace
/plugin install omnifamous-seo
```

## Plugins

### `omnifamous-seo`

Live SEO and AI-visibility data through the OMNIFAMOUS hosted MCP server, plus
two skills.

| Ships | What |
|---|---|
| MCP server | `https://api-production-c5b5.up.railway.app/mcp`, Streamable HTTP |
| Skill `omnifamous-seo` | When and how to use the tools |
| Skill `ai-visibility-research` | Primary-source research on what AI engines cite |

Two tools are free and need no credential. The rest need an agent key from
https://omnifamous.com/seo-mcp and are metered per successful call, at the price
published in each tool's description.

Full detail: [`plugins/omnifamous-seo/README.md`](plugins/omnifamous-seo/README.md).

## What these plugins do not do

No hooks, no commands, no agents, no scripts, no binaries. Installing registers
a remote MCP server and markdown skills. Nothing here executes on your machine,
and nothing reads your environment, dotfiles or keys.

## License

MIT. See [LICENSE](LICENSE).
