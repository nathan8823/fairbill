---
name: send-letter
description: Produce a formal letter and get it sent by certified mail (online service or USPS counter). Use for debt validation, 501(r) assertions, formal disputes, settlement offers, and anything the user may later need to prove was received.
---

# Formal letters + certified mail

Email is for speed; certified mail is for proof. Use paper when the letter
asserts a legal right, sets a deadline, makes a settlement offer, or answers
a collector.

## Produce the letter

1. Start from the right template in `templates/letters/`; personalize
   completely from the case file.
2. Formal letter layout: user's name/address, date, provider's billing
   address (from the bill — verify; disputes often go to a PO box that
   differs from the payment address), `RE: Patient <name>, Account
   #<number>, Date(s) of service <dates>`.
3. Include the magic line where applicable: **"This account is disputed.
   Please note the dispute in your records."** And always: **"Please respond
   in writing to the address above."**
4. Save as markdown in `cases/<case>/letters/`, then render a PDF for
   mailing. Check what's available and use the first that works:
   `pandoc x.md -o x.pdf`, `wkhtmltopdf`, `weasyprint`, or macOS
   `textutil -convert html` + `cupsfilter`. If nothing is installed, have
   the user open the .md and print to PDF — don't block on tooling.
5. **User reviews and approves the final PDF before anything is sent.**

## Send it — two paths (user picks)

**Online (~$8–12, no post office trip):**
- docupost.com — upload PDF, ~$7 + postage for Certified Mail
- simplecertifiedmail.com — certified specialist, per-letter pricing
- mailform.io — upload + Certified w/ Return Receipt

Walk the user through upload; you fill nothing on these sites yourself
unless the user explicitly asks and the data isn't payment credentials.

**USPS counter (~$5–10):**
Print the PDF → post office → "Certified Mail with Return Receipt" (the
green card, or electronic return receipt). Cheaper, same proof.

## Aftermath

- Tracking number, send date, and service used → `case.md`.
- Certified article number goes in the case file AND on the user's copy of
  the letter.
- Delivery confirmation (usps.com/tracking) → note the delivered date; that
  date starts their response clock. No response by deadline → follow-up
  letter cites "my letter delivered <date>, certified article #<number>" —
  that sentence is what escalation rungs are built from.
