---
name: compare-places
description: Compare crime across two or more U.S. addresses, cities or towns with CrimeMetric. Use when the user wants to know how places stack up on crime, violent crime or property crime.
---

# Compare places

1. For each street address call `crime_index`. For each city or town call `find_places`, then `place_profile` with its place_id.
2. Show one table: place, total, violent and property indexes, national percentile, 80% range, confidence, and the one-year change where there is one.
3. Point out overlapping ranges and low-confidence rows.

## How to present the numbers

- Lead with the national percentile (90 means higher than where 90% of U.S. residents live), then each index (100 = the U.S. rate per resident) with its 80% range and confidence.
- Say where ranges overlap or confidence is low: the difference may not be real.
- Describe places by their numbers only. Never call a place safe or unsafe, give letter grades, or tell anyone to avoid an area.
- CrimeMetric's terms forbid using the data for decisions about individual people (tenant screening, lending, insurance, hiring). If asked, say so and keep to places and properties.
