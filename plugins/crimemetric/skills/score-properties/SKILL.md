---
name: score-properties
description: Score a list of property addresses for crime with CrimeMetric, one row per property. Use for rental or investment portfolios, acquisition lists, or a spreadsheet or CSV of addresses.
---

# Score a property list

1. Read the addresses (from the message, a pasted list, or a CSV/spreadsheet file the user points to).
2. Call `account_status` once. On Developer or Business, call `crime_index_batch` with up to 10 locations at a time; on Free, call `crime_index` once per address (one request a second).
3. Return one table in the order given: the address as matched, block group, total, violent and property index with national percentile and confidence, and the index against the city. If the user gave a file, offer to write the results next to it as a CSV.
4. List any address that didn't match so the user can fix it.

## How to present the numbers

- Lead with the national percentile (90 means higher than where 90% of U.S. residents live), then each index (100 = the U.S. rate per resident) with its 80% range and confidence.
- Say where ranges overlap or confidence is low: the difference may not be real.
- Describe places by their numbers only. Never call a place safe or unsafe, give letter grades, or tell anyone to avoid an area.
- CrimeMetric's terms forbid using the data for decisions about individual people (tenant screening, lending, insurance, hiring). If asked, say so and keep to places and properties.
