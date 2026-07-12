---
name: intake
description: Start a new medical-bill case. Use when the user mentions any new bill, collection notice, or billing problem — builds the case file that every other skill works from.
---

# Intake — open the case

Goal: a complete case file, a screened set of opportunities, and a clear next
step, in one session.

## Steps

1. **Create the case folder**: `cases/<yyyy-mm-provider-context>/` (e.g.
   `cases/2026-07-st-marys-er/`). Copy `templates/case-file.md` in as
   `case.md`. Create an empty `call-log.md` and a `letters/` subfolder.

2. **Get the documents.** Ask the user to drop into the case folder (or
   share) whatever they have: the bill, any EOB, collection letters, the
   Good Faith Estimate if one was given. Read them with the Read tool
   (PDFs and photos both work). Extract into `case.md`: provider name and
   billing address/phone, account number, dates of service, total billed,
   every line item visible, insurance status, and all deadlines mentioned.

3. **Interview — only what the documents don't answer:**
   - What happened medically, in the user's words? (Flags upcoding: a
     "quick stitches" visit billed as Level 5 is a finding.)
   - Insured at the time? Did insurance process it — where's the EOB?
   - Emergency? Was any provider out-of-network? (No Surprises Act flags.)
   - Any estimate given beforehand? (GFE dispute flag.)
   - Has anything been paid, or a payment plan started?
   - Any collection contact yet? First contact date? (30-day validation clock.)
   - **With permission**, household size and approximate income —
     explain it's for charity-care screening and stays in the local case
     file only.
   - What outcome do they want, and what could they actually pay?

4. **Immediate triage — check in this order:**
   - Court summons in the papers? → stop, flag rule 5 of AGENTS.md, point
     to legal aid today, everything else is secondary.
   - Collector first contact <30 days ago? → debt validation letter now
     (`.claude/skills/collections/`), it's a hard deadline.
   - No itemized bill in hand? → that request goes out today
     (`templates/letters/itemized-request.md`).
   - Nonprofit hospital + income plausibly under ~4x federal poverty line?
     → run `.claude/skills/financial-assistance/` before negotiating.

5. **Write it all into `case.md`**, set the status line, and tell the user:
   what you found, the single next action, and who does it (you or them).

## Rules

- Personal data goes only in `cases/` (gitignored). Remind the user of this.
- Empathy first, plan second: many users arrive scared by a five-figure
  number. State early and plainly that first bills are opening numbers,
  errors are common, and there is a process.
