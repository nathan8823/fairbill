---
name: strategy
description: Choose the negotiation play and write the game plan — target number, sequence, escalation ladder, deadlines. Use once evidence is gathered (bill audited, prices benchmarked, assistance screened).
---

# Strategy — pick the play

Inputs from the case file: audit findings, benchmark table, assistance
screening, insurance posture, collections status, what the user can pay.
Output: a written game plan in `case.md` the user signs off on.

## The decision tree (first match wins as PRIMARY play; others stack behind it)

1. **Court summons exists** → not a negotiation. Legal aid, answer the
   summons, pause everything else.
2. **Collector involved & validation window open** → validate first
   (`collections` skill), negotiate after.
3. **Charity-care screening says likely eligible** → apply (`financial-
   assistance`); hold all payment; negotiation only for any remainder.
4. **No Surprises Act facts** (OON provider at in-network facility,
   emergency OON, or bill > GFE + $400) → rights-based dispute / PPDR
   (`rights-and-laws.md` §1, `templates/letters/nsa-complaint.md`), not a
   discount request.
5. **Confirmed billing errors** → error dispute letter first; negotiate the
   corrected balance after they respond.
6. **Insurance denied/underpaid wrongly** → `insurance-appeal` before
   paying anything.
7. **Bill is real, priced absurdly** (the common case) → evidence-based
   settlement: benchmark table + written offer.
8. **Bill is real and fairly priced** (rare, but happens — say so honestly)
   → hardship adjustment request + interest-free payment plan sizing.

## Writing the game plan

Put in `case.md`:

- **Primary play + stacked plays**, in order, each with its trigger
  ("if FAP denied → settlement offer at $X").
- **Numbers**: walk-away target, opening offer, absolute max the user can
  pay. Anchor all three to the benchmark table.
- **Channel sequence**: written where possible; phone to locate the right
  human, letters to commit positions. Certified mail for anything
  rights-based (`send-letter`).
- **Deadlines**: theirs and ours (validation clock, 240-day FAP window,
  PPDR 120 days, promised response dates). Every deadline gets a date.
- **Escalation ladder** with the specific next rung named
  (`knowledge/tactics.md`).

## Rules of engagement

- One position at a time: never simultaneously claim "I can't afford this"
  and "I'll pay $X today" to the same office. Sequence: rights/errors →
  assistance → money.
- Every phone commitment gets a same-day written recap.
- No payment until settlement terms are confirmed in writing ("payment in
  full," account number, amount, signature block).
- Present the plan to the user in dollars: "billed $14,200 → target $3,100,
  here's the path" — then get their go before executing.
