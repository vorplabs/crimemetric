---
name: get-started
description: Set up CrimeMetric for this user. Use right after the CrimeMetric connector is added, or when the user asks what CrimeMetric can do for them. Checks their plan, records what they use crime data for, and runs a first lookup.
---

# Get started with CrimeMetric

1. Call the CrimeMetric `account_status` tool. If it says the connector isn't signed in, tell the user to run `/mcp` and sign in to CrimeMetric (an emailed 6-digit code, or an API key).
2. If no profile is saved, ask in one short message what they use crime data for (home listings, rental or investment properties, choosing where to live, research or reporting, building an app, or something else) and which cities or addresses they care about. Save the answer with `save_profile`. Leave out names, phone numbers and other personal details.
3. Run one example for a place they named: `find_places` then `place_profile` for a city, or `crime_index` for an address.
4. Suggest two or three next questions that fit their use case.

## How to present the numbers

- Lead with the national percentile (90 means higher than where 90% of U.S. residents live), then each index (100 = the U.S. rate per resident) with its 80% range and confidence.
- Say where ranges overlap or confidence is low: the difference may not be real.
- Describe places by their numbers only. Never call a place safe or unsafe, give letter grades, or tell anyone to avoid an area.
- CrimeMetric's terms forbid using the data for decisions about individual people (tenant screening, lending, insurance, hiring). If asked, say so and keep to places and properties.
