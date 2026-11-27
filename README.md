# CrimeMetric for Claude, ChatGPT and other AI assistants

[CrimeMetric](https://crimemetric.com) gives crime rates for any U.S. address, city or neighborhood: modeled
indexes for 16 crime types against the U.S. rate, each with a national percentile, an 80% range and a confidence
level, plus city profiles and police-published incident records where available.

This repository holds the **Claude Code plugin** (the CrimeMetric connector plus skills) and the
[MCP Registry](https://registry.modelcontextprotocol.io) entry. The server itself runs at `api.crimemetric.com`.

## Connect

| Where | How |
|---|---|
| **Claude** (web, desktop, mobile) | [Add to Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=CrimeMetric&connectorUrl=https%3A%2F%2Fapi.crimemetric.com%2Fconnect), then Connect and sign in |
| **ChatGPT** | [chatgpt.com/plugins](https://chatgpt.com/plugins) > Add > Add custom MCP server > `https://api.crimemetric.com/connect`, OAuth |
| **Claude Code** | `claude plugin marketplace add vorplabs/crimemetric` then `claude plugin install crimemetric@crimemetric` |
| **Cursor, VS Code, others** | Remote MCP server (streamable HTTP): `https://api.crimemetric.com/connect` |

You sign in with a 6-digit code sent to your email (or an existing API key). New accounts are free: 1,000 lookups
a month. Clients that send a header instead of signing in can use `https://api.crimemetric.com/mcp` with
`Authorization: Bearer <key>` ([get a key](https://api.crimemetric.com/signup)). Place search, city profiles,
coverage and crime definitions work without a key.

Full setup: [crimemetric.com/api/connect](https://crimemetric.com/api/connect).

## After connecting

Paste this into a new chat:

```
I just connected the CrimeMetric connector. Please:
1. Run one example lookup right away for a U.S. street address or city I name (or Austin, TX if I haven't named one yet): use crime_index for an address (lead with the national percentile, and give each index with its 80% range and confidence), or find_places then place_profile for a city (report the city indexes where 100 = U.S. rate, the 1-year change, and neighborhood spread).
2. Call account_status to show my plan and remaining monthly lookups.
3. Suggest two or three things I could ask next. If no profile is saved yet, briefly ask what I use crime data for and offer to save it with save_profile (leaving out names and contact details).
```

## Skills in the Claude Code plugin

| Skill | For |
|---|---|
| `get-started` | Check your plan, save what you use CrimeMetric for, run a first lookup |
| `compare-places` | Two or more addresses, cities or towns in one table |
| `score-properties` | A list or CSV of property addresses, one row each |
| `research-a-move` | A city's rates, trend and spread across neighborhoods |
| `listing-facts` | Neutral, sourced figures for a home listing (fair housing) |
| `build-with-crimemetric` | Endpoints, code samples and limits for developers |

The same tasks are MCP prompts on the server, so Claude and other clients show them without the plugin.

## Tools

`crime_index`, `crime_index_batch`, `find_places`, `place_profile`, `place_block_groups`, `nearby_incidents`,
`incident_stats`, `data_coverage`, `crime_definitions`, `account_status`, `save_profile`. All read-only except
`save_profile`, which saves your own profile. See the [API reference](https://crimemetric.com/api/reference#mcp).

## Rules

The figures are modeled estimates and police-published records. They can't be used for decisions about individual
people, such as tenant screening, lending, insurance or hiring. See the [API terms](https://crimemetric.com/terms)
and [data terms](https://crimemetric.com/data-terms).

Support: support@vorplabs.com. CrimeMetric is made by [Vorp Labs](https://vorplabs.com).
