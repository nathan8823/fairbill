---
name: review-bill
description: Audit an itemized medical bill for errors — duplicates, upcoding, unbundling, phantom charges. Use once an itemized bill with CPT codes is in the case folder.
---

# Review the itemized bill

Prereq: an itemized statement with CPT/HCPCS codes in the case folder. If
there isn't one, send the request first (`templates/letters/itemized-request.md`)
— never audit a summary bill.

## Steps

1. **Transcribe** every line into a table in `case.md`: date, CPT/HCPCS,
   description, units, charge. Reading the bill into structured data IS the
   audit's foundation — most errors surface here.

2. **Decode the codes.** For each CPT, state in plain English what it is
   (and its E/M level if it's a visit code). Flag anything that doesn't
   match the story from intake. The user was there — walk the timeline with
   them: "You're billed for two chest X-rays — do you remember two?"

3. **Run the error checklist** (details in `knowledge/tactics.md` §3 and
   `knowledge/glossary.md`). Billing departments have insider names for the
   big four — use them; they signal you know the game:
   - **"Double dip"** — duplicates (same code + date, or same service under
     two revenue codes)
   - **"Level creep"** — upcoding (ER E/M level vs. what happened;
     observation billed as admission)
   - **"Unbundling"** — components billed alongside their bundle code
   - **"Phantom charges"** — drugs/supplies/tests not received; ordered
     then canceled but billed
   - Quantity errors (units column!) and impossible times (OR minutes, room days
     — the discharge-day room charge is a classic)
   - **Room-type charges**: private-room rates for shared rooms. The
     hospital's bed-management system logs every room/bed assignment by
     shift (ADT — admission/discharge/transfer records). Request them for
     any inpatient stay with room charges — see the optional items in
     `templates/letters/records-request.md`.
   - Wrong patient, date, or provider lines
   - If insured: EOB mismatch — any line where the provider's ask exceeds
     the EOB's patient responsibility

4. **Score each finding**: confirmed error / suspicious (needs their records)
   / fine. For "suspicious," the follow-up is a HIPAA records request
   (`templates/letters/records-request.md`) — medical records vs. bill is
   the definitive comparison.

5. **Write the dispute.** Confirmed + suspicious items go into
   `templates/letters/error-dispute.md`, itemized with codes, one paragraph
   per item, and land in `letters/` for user approval. Disputed amount is
   frozen; undisputed remainder proceeds to `benchmark-price` → `strategy`.

Never assert fraud — assert "these charges appear inconsistent with the
services received" and request correction and a corrected statement.
