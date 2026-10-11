# Realistic Demo Data

Demo data is part of the design. Meaningless data ("Project A", "Company 1", "User 123", "Lorem ipsum", `$1,000` everywhere) makes a sophisticated product look fake.

## Rules
1. **Fit the world.** Names, places, currencies, phone formats, company types, and regulators match the product's geography and industry (e.g. NGN/KES/GHS and Lagos/Nairobi/Accra for a pan-African fintech; ZIP codes and LLCs for US SMBs).
2. **Be specific.** "Kumasi Cold Chain Ltd — 12,000 m² cold-storage expansion, GHS 48.2M, Series A, due diligence" beats "Project 1, $1M, active".
3. **Distributions, not constants.** Values follow plausible distributions (a few large, many small); dates spread over realistic time ranges relative to *today*; statuses distributed like a real pipeline (many early-stage, fewer late-stage, some stalled/rejected).
4. **Tell stories.** Seed a few connected narratives across entities — an organization with users, a deal with documents, messages, an audit trail, and an AI recommendation that references them.
5. **Cover every state.** Include records in each lifecycle state, plus edge cases: long names, missing optional fields, overdue items, failed payments, a rejected application.
6. **Per-audience datasets.** Each role's demo login sees data that looks like *their* world.
7. **Fictional and labelled.** Do not use real private individuals. Avoid real companies unless they are public facts used accurately (e.g. a real stock exchange name in a market-data context). Where a real organization is mentioned, don't imply endorsement. Mark demo environments with a "Demo data" indicator and document that seeds are fictional. Keep verified real-world data (e.g. official statistics) separate and cite its source.
8. **Deterministic seeds.** Use a seeded generator (e.g. Faker with a fixed seed + hand-written hero records) so screenshots and tests are stable.

## Checklist for each seed set
- [ ] 3–8 hand-crafted "hero" records used in marketing screenshots and demos
- [ ] 30–300 generated records for lists, tables, charts
- [ ] Time series long enough to make charts meaningful (e.g. 12–24 months)
- [ ] Messages and documents with realistic titles and short believable content
- [ ] Notifications and activity feed entries referencing real seeded entities
- [ ] Demo accounts per role with documented credentials (demo-only)
