---
name: get-started
description: Set up CrimeMetric for this user. Use right after the CrimeMetric connector is added, or when the user asks what CrimeMetric can do for them. Signs in if needed, runs a first lookup right away, checks their plan, and optionally records their use case.
---

# Get started with CrimeMetric

1. Check connection state first. This plugin connects over OAuth (`/connect`), so if the CrimeMetric tools aren't available yet or return an authorization error, tell the user to run `/mcp` and sign in with the 6-digit emailed code (or an API key) — it takes under a minute and includes 1,000 free lookups a month.
2. Once connected, deliver a useful lookup right away. If the user named a U.S. street address or city, look it up immediately (`crime_index` for an address, or `find_places` then `place_profile` for a city); if not, run a quick city example for Austin, TX (`find_places` + `place_profile`) so they see real output immediately.
3. Call `account_status` to show their plan and remaining monthly lookups.
4. Suggest two or three follow-up questions that fit what they asked. If no profile is saved yet, briefly ask what they use crime data for (home listings, rental or investment properties, choosing where to live, research or reporting, building an app, or something else) and offer to save it with `save_profile`, leaving out names, phone numbers and other personal details.

## How to present the numbers

- **For an address or census block group (`crime_index`):** lead with the national percentile (90 means higher than where 90% of U.S. residents live), then report each index (100 = the U.S. rate per resident) with its 80% range (`index_p10`–`index_p90`) and confidence level. Note where ranges overlap or confidence is low.
- **For a city or town (`place_profile`):** report the modeled city indexes (100 = the U.S. rate per resident), the 1-year change where available, and how crime varies across the city's neighborhoods (quartiles / spread).
- Describe places by their numbers only. Never call a place safe or unsafe, give letter grades, or tell anyone to avoid an area.
- CrimeMetric's terms forbid using the data for decisions about individual people (tenant screening, lending, insurance, hiring). If asked, say so and keep to places and properties.
