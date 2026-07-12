---
name: benchmark-price
description: Establish the fair price for billed services using Medicare rates, the hospital's own transparency file, and regional benchmarks. Use after review-bill, before making any offer.
---

# Benchmark the price

Goal: for every significant line on the bill, a table showing what people
with leverage pay — so the user's offer is a documented number, not a plea.
Full tool details and URLs: `knowledge/benchmarks.md`.

## Steps

1. **Pick the lines that matter** — the top charges covering ~90% of the
   bill. Don't benchmark $12 line items.

2. **Medicare rate per CPT** — the floor and the universal reference. Use
   the CMS lookup tools per `knowledge/benchmarks.md`, localized to the
   user's area.

3. **The hospital's own prices** — find its machine-readable standard
   charges file (try `<hospital site>/standardcharges`, the site's price
   transparency page, or the aggregators listed in the knowledge doc). Pull,
   for each CPT: the **cash price** and the **payer-negotiated rate range**.
   This is the strongest possible anchor: their own published numbers.

4. **Regional benchmarks** — FAIR Health Consumer / Healthcare Bluebook for
   the same codes + zip, as a sanity check and a second citation.

5. **Build the table** in `case.md`:

   | CPT | Billed | Medicare | Their cash price | Insurers pay | Fair target |
   |-----|--------|----------|------------------|--------------|-------------|

6. **Set the target and the ask.** Default fair-target logic: the lowest
   defensible anchor that exists in *their* documents — usually their cash
   price or the low end of their negotiated range; if neither is findable,
   1.5–2x Medicare. State the total target and the opening offer (open
   below target, leave room) in `case.md` for the `strategy` skill.

If the hospital publishes no usable file, record that fact — noncompliance
with the transparency rule is itself leverage ("I attempted to verify these
charges against your standard-charges file, which I could not locate;
CMS requires…").
