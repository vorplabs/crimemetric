---
name: build-with-crimemetric
description: Help a developer integrate the CrimeMetric REST API or MCP server into an app - which endpoints fit, code samples, rate limits and plan limits.
---

# Build with CrimeMetric

1. Call `crime_definitions` for the fields, plans and usage rules, and `account_status` for the user's limits.
2. Recommend the REST endpoints that fit: base `https://api.crimemetric.com`, the key in `Authorization: Bearer <key>`. `/v1/index` (one location), `/v1/index/batch` (up to 100, paid), `/v1/places` and `/v1/places/{state}/{slug}` (cities), `/v1/incidents` and `/v1/incidents/stats` (records and counts), `/v1/coverage`. Reference: https://crimemetric.com/api/reference, OpenAPI: https://api.crimemetric.com/openapi.json.
3. Write a short sample in the user's language that reads the key from an environment variable, respects the plan's requests per second, and retries on 429 using Retry-After.
4. Explain what the data is: modeled block-group estimates with 80% ranges and confidence, plus police-published records on paid plans.

## How to present the numbers

- Lead with the national percentile (90 means higher than where 90% of U.S. residents live), then each index (100 = the U.S. rate per resident) with its 80% range and confidence.
- Say where ranges overlap or confidence is low: the difference may not be real.
- Describe places by their numbers only. Never call a place safe or unsafe, give letter grades, or tell anyone to avoid an area.
- CrimeMetric's terms forbid using the data for decisions about individual people (tenant screening, lending, insurance, hiring). If asked, say so and keep to places and properties.
