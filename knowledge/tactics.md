# The tactics library

The core insight, straight from billing insiders: **the first bill is an
opening number, not a debt.** Hospital "chargemaster" prices are list prices
nobody with leverage actually pays — insurers typically pay a negotiated
fraction, Medicare pays less still, and cash prices are often below what
insured patients get balance-billed. Your job is to find out what people
with leverage pay, and get that price.

## The plays, in order

### 1. Stop the clock, start the file
Acknowledge the bill exists (never ignore it), but do not pay it. Calling the
billing office to say "I'm reviewing this bill and have requested an itemized
statement; please note the account is in dispute" pauses most collection
timelines in practice. Get every commitment logged: date, person, reference
number.

If insured, add the timing check: hospital statements typically go out
**before the insurance claim is even submitted** (coding takes days to
weeks; the patient statement is instant). Ask "has this claim been
submitted to my insurance, and on what date?" — and never pay before the
EOB exists and matches the bill. The EOB is the only document that shows
what is actually owed (see `inside-the-machine.md`).

### 2. Demand the itemized bill
Request "a fully itemized statement with CPT/HCPCS codes and descriptions for
every charge" — not the summary bill. Providers routinely send a one-line
"balance due" statement; you are entitled to the detail. No itemized bill =
no payment. This single step kills a surprising number of junk charges,
because billers know an itemized bill invites an audit.

### 3. Audit the line items
Roughly half of hospital bills contain at least one error. The classics:

- **Duplicate charges** — same code, same date, billed twice.
- **Upcoding** — a higher-severity code than the care delivered (e.g., a
  Level 5 ER visit, 99285, for a minor issue).
- **Unbundling** — charging separately for items included in a bundled
  procedure code.
- **Phantom charges** — services, drugs, or supplies never received; full-day
  room charges for the discharge day; operating-room time rounded up.
- **Wrong patient/date/insurance** — clerical errors that cascade.
- **Canceled work** — tests ordered then canceled, but billed.

Every confirmed error gets disputed in writing before any negotiation on the
remainder — errors destroy the biller's credibility and set the tone.

### 4. Benchmark every big line
See `knowledge/benchmarks.md`. For each significant CPT code, record:
Medicare rate, the hospital's published cash price, and the range insurers
pay at that hospital (from its own transparency file). The gap between
billed charges and these numbers is your negotiation room — and it is
usually enormous (3–10x Medicare is common).

### 5. Charity care before negotiation
If the hospital is nonprofit (most are), it is required by IRS 501(r) to have
a Financial Assistance Policy. Many patients qualify without being poor —
thresholds of 2–4x the federal poverty level are common, and many policies
cover *insured* patients too (see `objections.md` for the "only for
uninsured" myth). You can typically apply up to 240 days after the first
post-discharge bill — even after paying, even in collections. Screen every
case for this first: 100% forgiveness beats any negotiated discount.

### 6. The self-pay arbitrage
If insured but facing a huge patient share, compare against the cash/self-pay
price in the hospital's transparency file. Sometimes the cash price is lower
than your post-insurance balance. You can ask to be rebilled as self-pay
(weigh: payments then don't count toward your deductible).

### 7. The evidence-based settlement offer
Once armed (errors found, benchmarks recorded, assistance screened), make a
specific written offer with the reasoning attached: "Medicare pays $X for
these services; your own published cash price is $Y; I can pay $Z within 15
days of written confirmation that this settles the account in full." Round
numbers, short deadline, prompt-pay framing. Billing departments have
standing authority for 20–50% reductions; documented-error cases and
lump-sum offers do better.

### 8. Payment plan as the fallback, never the goal
If no reduction lands, a payment plan directly with the provider at $0
interest is the floor — never a medical credit card (CareCredit-style
deferred-interest products turn medical debt into consumer debt at 27%+ and
extinguish your negotiation leverage). Keep the plan small enough to never
miss; a live payment plan usually blocks collections referral.

## The escalation ladder

Work it one rung at a time; each rung is cited in the letter to the next.

1. Billing representative (phone + written recap)
2. Billing supervisor / "patient financial services"
3. Hospital **patient advocate / ombudsman** (they exist; they can move bills)
4. Written dispute to the billing department (certified mail), **CC the
   hospital's compliance office** — compliance answers for regulatory
   exposure and has authority billing does not (`inside-the-machine.md`)
5. Hospital administration — patient experience office, then CFO's office
6. Regulators, as fits the facts:
   - No Surprises Act violation → CMS complaint (cms.gov/nosurprises, 1-800-985-3059)
   - 501(r)/charity-care failure → state Attorney General + IRS Form 13909
   - Collections abuse → CFPB complaint (consumerfinance.gov/complaint)
   - Insurance misconduct → state insurance commissioner
7. Local journalism / social media — hospitals settle fast when a documented
   story is about to run. A media inquiry routes straight to the PR office
   and the executive chain, bypassing the billing queue entirely. Last
   rung, real leverage — and **only ever reference media contact that has
   actually happened**. Implying press involvement that doesn't exist
   violates rule 6 (don't fabricate) and hands the hospital's counsel a
   reason to dismiss everything else in the file.

Two cross-cutting leverage facts for the letters at rungs 4–6: the
hospital's patient-experience scores are tied to Medicare money
(`rights-and-laws.md` §9), and its Form 990 shows exactly how much charity
care went unspent next to executive pay (`.claude/skills/financial-assistance/`).

## Timing leverage

- **Before treatment:** ask for the Good Faith Estimate (self-pay) or
  pre-authorization + in-network confirmation in writing (insured).
- **240-day window:** charity-care applications generally remain open 240
  days from the first post-discharge bill.
- **Before collections referral** (usually 90–180 days): providers have the
  most flexibility while they still own the debt.
- **Fiscal year-end** (often June 30 or Dec 31 for hospitals): billing
  departments clear books and approve settlements faster.
- **In collections:** the agency bought or works the debt at a steep
  discount — settlement room is often larger, but validate the debt first
  (see `.claude/skills/collections/`).
- **Before a merger closes:** hospital mergers are announced months ahead,
  and research consistently finds prices rise after them. Assistance
  programs, payment plans, and billing systems also get restructured.
  Anything in flight — a charity-care enrollment, a payment plan, a
  settlement — should be locked in writing at current terms before the
  new entity takes over.

## Paper-trail discipline

- Every call gets a written recap email the same day ("Per our call today
  with [name], you confirmed…"). Unrecapped calls didn't happen.
- Every deadline they state, and every one you set, goes in the case file.
- Certified mail for anything you may later need to prove was received.
- Never state in writing that you "owe" an amount while disputing it — say
  "the amount claimed."

## Proportionality

The plays above assume a bill worth fighting. Always do the cheap steps —
itemized bill, error scan, charity-care screen, a benchmark glance — but if
they come back clean on a modest bill, the fair move is to close it: ask for
the cash price or a prompt-pay discount once, take the answer, and pay.
Dragging a correct $180 bill through the escalation ladder risks collections
and credit noise over nothing. Fight the asymmetry, not the arithmetic.

## What not to do

- Don't pay anything while a dispute or assistance application is pending —
  partial payment can be read as accepting the bill (and in collections, can
  restart the statute of limitations).
- Don't put medical debt on a credit card — you convert protected,
  negotiable, interest-free debt into unprotected consumer debt.
- Don't accept phone-only settlements. Writing first, then money.
- Don't exaggerate hardship or fabricate anything. Documented facts win.
- Don't miss a court date over a negotiation — a summons changes the game;
  answer it and get legal aid (lawhelp.org).
