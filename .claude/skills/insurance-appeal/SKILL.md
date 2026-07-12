---
name: insurance-appeal
description: Appeal an insurance denial or underpayment — internal appeal, then external review. Use when the EOB shows denied claims, out-of-network processing, or "not medically necessary" determinations.
---

# Insurance appeal

Roughly half of appealed denials get overturned — and almost nobody appeals.
The appeal is often worth more than any provider-side negotiation, so run it
before conceding the balance is really the user's. Deadlines and legal
frame: `knowledge/rights-and-laws.md` §7.

## Steps

1. **Read the EOB + denial letter.** Extract: the denial reason code and its
   plain-English meaning, the deadline to appeal (typically 180 days from
   denial), and the plan's appeal address/portal. Common denial classes and
   their attacks:
   - **Not medically necessary** → treating physician letter is the whole
     game; request one, and cite the plan's own medical policy for the
     service (findable on the insurer's site).
   - **Out-of-network** → was it an emergency, or an OON provider at an
     in-network facility? That's a No Surprises Act violation, not a valid
     denial (`rights-and-laws.md` §1).
   - **No prior authorization** → whose job was the auth? If the in-network
     provider failed to obtain it, the plan's own rules usually say the
     member isn't liable; also ask the provider to write it off for their
     own error.
   - **Coding/clerical** → the fix is a corrected claim from the provider,
     not an appeal; call the provider's billing office first.
2. **Gather the record**: medical records for the service (HIPAA request via
   `templates/letters/records-request.md` if needed), the physician support
   letter, the plan document/policy language (ask the employer's HR for the
   SPD if employer-sponsored).
3. **Write the internal appeal** — `templates/letters/insurance-appeal.md`:
   member/claim numbers, the determination being appealed, the specific plan
   language, the clinical facts, the ask ("process at the in-network benefit
   level" / "cover as medically necessary"), exhibits listed. Send by the
   plan's stated channel + keep proof. User approves before sending.
4. **Track the clock**: plans owe a decision in 30 days (pre-service) /
   60 days (post-service) for most plans. Expedited if health is at risk.
5. **External review** — internal appeal upheld? File for independent
   external review within 4 months (federal) or per state rules; the
   reviewer's decision binds the plan. The denial letter must explain how.
6. **Freeze the provider side** meanwhile: tell billing the claim is under
   appeal and ask for a hold — most will pause rather than collect a balance
   that may vanish.
