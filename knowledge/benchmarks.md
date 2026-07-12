# Price Benchmarks: Establishing a Fair Price for Each Billed Code

Purpose: given the CPT/HCPCS codes on a bill, establish what a FAIR price is for each line item. Every negotiation letter or call should anchor to numbers gathered here, not to the hospital's billed charges. Record every benchmark you find in the case file with its source and date retrieved.

> Disclaimer: prices, URLs, and tools change frequently — verify each figure at time of use (this file last verified July 2026).

## 1. Medicare Rates — The Anchor

Medicare's payment rates are the closest thing the US has to a reference price. The core negotiation frame:

- Hospitals and physicians accept roughly **1.0–2.5x Medicare** from commercial insurers (RAND's employer transparency study found private plans paid hospitals an average of **254% of Medicare** in 2022 — inpatient 254%, outpatient 279%, professional services 184%).
- Billed "chargemaster" charges are often **3–10x Medicare** and almost nobody actually pays them.
- Therefore an offer in the 1.5–2.5x Medicare range is what insurers themselves pay, and is presumptively fair for a self-pay patient.

Medicare has **different fee schedules for different service types** — use the right one per code:

### Physician/professional services (most 5-digit CPT codes: office visits, surgery professional fees, imaging reads)
Tool: **CMS Physician Fee Schedule Look-Up** — https://www.cms.gov/medicare/physician-fee-schedule/search

How the agent does this:
1. Open the search page. Select the current year, search type "Pricing Information," enter the CPT/HCPCS code.
2. Choose MAC/locality (pick the patient's state locality; "National Payment Amount" is fine for a first pass).
3. Record the **non-facility price** (office setting) or **facility price** (hospital setting) — this is the Medicare-allowed amount.
4. Note in the case file: code, Medicare allowed $, locality, year.
5. If the page blocks automated fetching (it 403s bots), ask the user to open the URL and read the number back, or use the downloadable PFS files at https://www.cms.gov/medicare/payment/fee-schedules/physician

### Lab tests (CPT 80000-series and most pathology)
Lab codes are NOT on the Physician Fee Schedule. Use the **Clinical Laboratory Fee Schedule (CLFS)**:
- Quarterly rate files (CSV/XLSX with national rate per code): https://www.cms.gov/medicare/payment/fee-schedules/clinical-laboratory-fee-schedule-clfs/files
- Download the current quarter file (e.g. "26CLABQ3"), find the code's row, record the national payment rate.

### Hospital outpatient procedures
Tool: **Medicare Procedure Price Lookup** — https://www.medicare.gov/procedure-price-lookup/
1. Enter the CPT/HCPCS code or procedure name (~3,900 procedures covered).
2. Record the national average **total Medicare payment** for hospital outpatient department vs ambulatory surgical center. This bundles the facility fee — useful when the bill has facility charges.
3. Consumer-friendly; no login. (Direct code URLs work: `https://www.medicare.gov/procedure-price-lookup/cost/<code>/`.)

### Inpatient stays (DRG-based)
There is no simple consumer tool for inpatient DRG rates. Use the hospital's own transparency file (Section 4) as the primary benchmark instead, or FAIR Health for the market context.

## 2. FAIR Health Consumer — Regional Market Benchmarks

**https://www.fairhealthconsumer.org** — free, no registration, also in Spanish. Built on the largest private claims database in the US. Gives the range of what providers charge and what insurers pay in the patient's region ("geozip" = first 3 digits of ZIP), across percentiles.

How the agent does this:
1. Go to fairhealthconsumer.org → "Medical Costs" lookup.
2. Enter the patient's ZIP code and the procedure (search by CPT code or name).
3. Record both the **in-network (insurer-paid) estimate** and the **out-of-network (billed charge) estimate** for the area.
4. Use the in-network figure as a "what insurers actually pay near you" data point; if the billed charge exceeds FAIR Health's out-of-network benchmark, note that the charge is above even the local billed-charge norm — strong letter material.

## 3. Healthcare Bluebook (now "Valenz Bluebook")

Healthcare Bluebook was acquired by Vālenz Health (2024); the consumer tool survives at **https://www.healthcarebluebook.com/ui/findfairprice** (the bare homepage now redirects to valenzhealth.com — use the /ui/ path).

- Its **"Fair Price"** = the reasonable amount to pay in the patient's market, derived from actual negotiated/paid amounts — typically far below billed charges. Results are color-coded (green = at/below Fair Price).
- Full features are often gated behind an employer benefit login; the free lookup covers common shoppable procedures.

How the agent does this:
1. Open the findfairprice URL, search the procedure by name, enter ZIP.
2. Record the Fair Price for the market. If the tool requires an employer code the patient doesn't have, skip — FAIR Health + hospital files cover the same ground.

## 4. Hospital Price Transparency Files — The Strongest Anchor

Since 2021 (45 CFR Part 180), every US hospital must post a machine-readable file (MRF) of its standard charges, including for each code: **gross charge, discounted cash price, and every payer-specific negotiated rate**, de-identified min/max. Free, no login, accessible to automated download by law.

**The key trick:** look up the **cash price** and the **negotiated rates other insurers pay for the exact same code at the same hospital**. "Hospital X accepts $Y from Aetna for this exact service, and its own posted cash price is $Z" is the single strongest anchor available — it is the hospital's own published number.

How the agent does this:
1. **Find the file.** Try, in order:
   - Google/search: `"<hospital name>" standardcharges` or `site:<hospital-domain> standardcharges`
   - Try `https://<hospital-domain>/standardcharges` or the hospital's "Price Transparency"/"Pricing" page (usually footer-linked).
   - The file is named per CMS convention: `<EIN>_<hospital-name>_standardcharges.json` or `.csv`.
   - **PatientRightsAdvocate Hospital Price Files Finder**: https://hospitalpricingfiles.patientrightsadvocate.org/ — searchable directory of MRF links for ~6,000 hospitals. PRA also publishes semi-annual compliance reports (https://www.patientrightsadvocate.org/).
2. **Extract the code's row(s).** Download the file (may be large — hundreds of MB JSON; use `grep`/`jq`/pandas on the CPT code, and match the setting: outpatient vs inpatient).
3. **Record in the case file:** gross charge, **discounted cash price**, each payer-specific negotiated rate (name the payers), and de-identified min/max.
4. **Aggregators when the hospital file is unusable:**
   - **Turquoise Health patient search** — https://turquoise.health/patients — free comparison of bundled prices by service + ZIP; good for cross-hospital context.
   - **Dolthub hospital price databases** (https://www.dolthub.com/repositories/dolthub/hospital-price-transparency-v3 and `transparency-in-pricing`) — free SQL-queryable dumps, BUT collection stopped around 2023–24; treat as stale, use only for historical context.
5. A 2023 Health Affairs / Johns Hopkins analysis of 70 shoppable services found the **cash price was at or below the median insurer-negotiated rate in 47% of cases** — cite this when arguing the cash price is a legitimate payment level, not a favor.

## 5. Good Faith Estimate Comparison (Self-Pay Patients)

Under the No Surprises Act, uninsured/self-pay patients must receive a **Good Faith Estimate (GFE)** when scheduling (or on request, 3+ business days ahead). Consumer explainer: https://www.cms.gov/medical-bill-rights

How the agent does this:
1. Ask the patient if they received a GFE (paper or portal). Get a copy into the case file.
2. Compare the final bill to the GFE line by line.
3. If the bill is **$400 or more above** the GFE, the patient can file a **Patient-Provider Dispute Resolution (PPDR)** case with HHS within **120 days** of the bill date (small admin fee, ~$25). While a dispute is pending, the provider cannot send the bill to collections or retaliate. Provider-side rules: https://www.cms.gov/nosurprises/providers-payment-resolution-with-patients
4. Even below the $400 threshold, a bill exceeding the GFE is leverage — quote the GFE amount as the expected price.

## 6. Worked Example — CPT 80053 (Comprehensive Metabolic Panel)

Bill shows: **CPT 80053, billed $195** (hospital outpatient lab).

1. **Medicare rate:** 80053 is a lab code → CLFS, not PFS. The 2026 CLFS national rate is **~$10.33**. Record: "Medicare pays ~$10.33 (CLFS 2026)."
2. **Hospital's own file:** find Hospital X's `standardcharges` file, grep for 80053. Suppose it shows: gross charge $195, **cash price $35**, negotiated rates $12–$48 across payers. Record all of them.
3. **FAIR Health:** ZIP lookup shows local insurers typically pay ~$25 for a CMP. Record.
4. **Analysis:** billed charge is ~19x Medicare and 5.6x the hospital's own cash price. Even the highest insurer pays $48.
5. **Fair offer:** open at Medicare-plus: ~$15–20 (1.5–2x Medicare). Settlement target: at or below the **$35 cash price**. Never pay above the highest negotiated rate ($48).
6. **Script:** "Medicare pays $10.33 for this test. Your own posted cash price is $35, and insurers pay you $12–48. I'll pay $20 today to resolve this line."

## 7. The Fair-Offer Formula

For each code, after gathering benchmarks:

```
M = Medicare rate (PFS / CLFS / Procedure Price Lookup)
C = hospital's posted discounted cash price (MRF)
N_low, N_high = lowest / highest payer-negotiated rate at this hospital (MRF)
F = FAIR Health in-network benchmark for the ZIP

Opening offer  = max(1.0 × M, N_low if known)        # what the best-negotiating insurer pays
Fair target    = min(C, 1.5–2.0 × M)                  # whichever framing is stronger
Walk-away max  = min(2.5 × M, N_high, C)              # never exceed what any insurer pays
```

Pick the **framing that is stronger** for this bill:
- If the cash price is low → anchor on "your own posted cash price is $C."
- If the MRF is missing/noncompliant → anchor on Medicare multiples ("commercial insurers average ~2.5x Medicare per RAND; I'm offering 2x") and note the transparency-rule noncompliance itself as leverage.
- If a GFE exists and is exceeded → anchor on the GFE and the $400 PPDR right.
- Supporting stats to cite: RAND Round 5.1 (private plans pay ~254% of Medicare, 2022 data); Health Affairs/Johns Hopkins 2023 (cash price ≤ median negotiated rate at 47% of hospitals). Prompt-pay/lump-sum settlements at 40–70% off billed charges are routine hospital practice — but always ground the specific number in M, C, and N, not a generic percentage.

Log in the case file per code: `code | billed | M | C | N_low–N_high | F | opening | target | max | sources+dates`.

## Sources (verified July 2026)

- CMS Physician Fee Schedule Look-Up: https://www.cms.gov/medicare/physician-fee-schedule/search (overview: https://www.cms.gov/medicare/physician-fee-schedule/search/overview)
- CMS Clinical Laboratory Fee Schedule files: https://www.cms.gov/medicare/payment/fee-schedules/clinical-laboratory-fee-schedule-clfs/files
- Medicare Procedure Price Lookup (outpatient): https://www.medicare.gov/procedure-price-lookup/
- FAIR Health Consumer: https://www.fairhealthconsumer.org
- Valenz (Healthcare) Bluebook consumer lookup: https://www.healthcarebluebook.com/ui/findfairprice
- Hospital price transparency rule: https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-E/part-180 ; CMS tools/repo: https://github.com/CMSgov/hospital-price-transparency
- PRA Hospital Price Files Finder: https://hospitalpricingfiles.patientrightsadvocate.org/ ; reports: https://www.patientrightsadvocate.org/
- Turquoise Health patient search: https://turquoise.health/patients
- Dolthub hospital price DBs (stale): https://www.dolthub.com/repositories/dolthub/hospital-price-transparency-v3
- Medical bill rights / GFE + PPDR: https://www.cms.gov/medical-bill-rights ; https://www.cms.gov/nosurprises/providers-payment-resolution-with-patients
- RAND Round 5.1 (254% of Medicare): https://www.rand.org/pubs/research_reports/RRA1144-2-v2.html
- Cash vs negotiated prices (Health Affairs / Johns Hopkins): https://publichealth.jhu.edu/2023/study-finds-hospitals-cash-prices-for-uninsured-often-lower-than-insurer-negotiated-prices
