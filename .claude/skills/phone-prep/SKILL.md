---
name: phone-prep
description: Build a one-page phone brief — goal, script, questions, comebacks — before the user calls a billing office, insurer, or collector. Also handles the post-call debrief.
---

# Phone prep

You can't make the call; you make the caller unbeatable. Billing reps do
this all day — the user does it once, scared. The brief closes that gap.

## Before the call: the one-page brief

Write `cases/<case>/call-brief-yyyy-mm-dd.md`, phone-screen friendly
(the user will read it mid-call):

1. **Goal** — the single thing this call must produce (usually: a name, a
   fact, or a written follow-up commitment — almost never a payment).
2. **Opening statement** — 2–3 sentences, verbatim, with account number.
3. **The questions** — 5–10, ordered, with blanks to fill:
   - Always first: "Who am I speaking with, and what's a reference number
     for this call?"
   - Then the case-specific ones (examples): "What is the status of my
     itemized-statement request from <date>?" / "Is this account on hold
     while my financial-assistance application is pending?" / "What
     discount is available if this is settled as a lump sum?" / "Can you
     email me that in writing today?"
   - Always last: "Please note the account is in dispute. What did you
     record?"
4. **Likely pushback + comebacks** — pull the 3–4 relevant entries from
   `knowledge/objections.md`, quoted ready-to-say.
5. **Do-not lines** — what the user must NOT do on this call. Default:
   don't agree to any payment or plan, don't state income figures to a
   collector, don't say "I owe"; say "the amount claimed." For collectors:
   don't confirm the debt is theirs before validation.
6. **Capture sheet** — name / department / reference # / promises / deadlines.

Rehearse the opening with the user once if they want. Remind them: polite,
brief, endlessly repetitive is the winning style — reps escalate persistent
callers and stonewall angry ones.

## After the call: debrief

Ask what happened, fill the capture sheet into `call-log.md`, then
immediately draft the same-day written recap email (`draft-email`):
"Per our call today with <name>, reference #<n>, you confirmed…" — the
recap converts a phone promise into evidence. Update deadlines in `case.md`
and name the next action.
