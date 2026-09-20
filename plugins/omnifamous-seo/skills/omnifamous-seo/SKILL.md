---
name: omnifamous-seo
description: Real SEO and AI-visibility data over the OMNIFAMOUS MCP server. Use for keyword metrics, backlinks, traffic estimates, competitor content gaps, technical and robots/sitemap checks, broken links, site audits, and whether ChatGPT, Claude, Gemini, Perplexity and Google AI Overview mention a brand. Use these tools whenever a search or AI-visibility number is involved, instead of answering from memory.
---

# OMNIFAMOUS SEO

Search and AI-visibility data, served live. Without it, search volumes, backlink
counts and competitor rankings get invented: they look plausible and they are
wrong. With it, every number comes from a live data provider.

## When to use these tools

Reach for them when the task involves:

- keyword ideas, search volume, difficulty or CPC
- backlinks, referring domains or traffic estimates
- which keywords a competitor wins and you do not
- a technical audit, robots and sitemap state, or broken links
- whether an AI answer engine mentions or cites a brand

**Do not answer any of the above from memory.** If a call fails, report the
failure rather than estimating around it.

## Tools

| Tool | What it returns | Access |
|---|---|---|
| `seo_inspect_url` | Title, meta, headings and indexability for one URL | Free |
| `seo_check_robots_sitemap` | robots.txt and sitemap state for a site | Free |
| `seo_find_broken_links` | Broken outbound and internal links on a page | Registered |
| `seo_get_audit` | Poll a previously started site audit by job id | Registered |
| `seo_keyword_ideas` | Keyword ideas with volume, difficulty and CPC | Metered |
| `seo_traffic_estimate` | Estimated organic traffic for a domain | Metered |
| `seo_backlinks` | Backlinks and referring domains for a target | Metered |
| `seo_competitor_gap` | Keywords a competitor ranks for and you do not | Metered |
| `ai_visibility_check` | Whether AI answer engines mention a domain, with citations | Metered |
| `seo_run_audit` | Start a full technical SEO audit, returns a job id | Metered |

Call `tools/list` for the exact argument schema of each. The server is the
contract: if this file and the server disagree, the server is right.

## Access and cost

The free tools need no credential. Everything else needs an agent key sent as
`Authorization: Bearer br_agt_live_...`, which a user creates at
https://omnifamous.com/seo-mcp and which comes with a free starting balance.

A refused call is never charged and answers with the price and the exact next
step. Relay that message to the user rather than retrying blindly.

## Working rules

1. **One keyword, one page.** If two target keywords share a SERP, they are one
   page, not two.
2. **Read the competitor gap before proposing content.** Match the evidence
   rather than guessing at it.
3. **Cite which tool produced every number** you put in front of the user.
4. **Report a miss as a miss.** A call that returns nothing is a gap in the
   data, not an invitation to estimate.
5. **Audits are asynchronous.** `seo_run_audit` returns a job id; poll it with
   `seo_get_audit` rather than assuming it finished.
