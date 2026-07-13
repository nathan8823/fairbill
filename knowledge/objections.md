# Objection handling — what they'll say, and what to say back

Every one of these is a real response patients report getting. Billing staff
are trained to end calls with a payment or a payment plan; these comebacks
are how the user stays on script. Prep the relevant ones before every call
(`.claude/skills/phone-prep/`).

## "Financial assistance is only for the uninsured."

Usually false, always checkable. IRS 501(r) requires nonprofit hospitals to
have a written Financial Assistance Policy, and most FAPs cover
*underinsured* patients — eligibility is income-based, not
insurance-status-based.

> "I'd like a copy of your written Financial Assistance Policy, which
> you're required to maintain under IRS section 501(r). I'll determine my
> eligibility from the policy itself, not over the phone. Please also send
> the application."

If they refuse: the FAP is required to be posted publicly — find it on the
hospital website and quote its own eligibility table back to them.

## "We can't adjust this bill." / "There's nothing I can do."

Often true *for that person*. Never argue with the front line — reroute.

> "I understand you may not have the authority. Who does? Please transfer
> me to a billing supervisor or your patient financial advocate, and note
> in the account that the bill is in dispute."

## "You need to pay something today to keep this out of collections."

Payment-under-pressure is their best move and your worst.

> "I won't be making a payment while the account is in dispute. Please note
> the dispute in the account. I've requested an itemized statement and will
> respond in writing within [X] days of receiving it."

(And never authorize a "small good-faith payment" in collections — it can
restart the statute of limitations.)

## "It's already been sent to collections."

Nothing is over. Options, in order: ask the *provider* to recall the debt
(they often can, especially if a charity-care application or documented
dispute was pending); send the collector a debt-validation letter within 30
days of first contact; negotiate with the collector, who has more discount
room than the provider did. See `.claude/skills/collections/`.

## "We don't provide itemized bills." / it never arrives

> "Under HIPAA I have a right of access to my records, including billing
> records. Please send a fully itemized statement with CPT codes to the
> address on file within 30 days. I'm noting this request in writing today;
> the account is in dispute until it arrives."

Log the request date. A provider that pursues collections while stonewalling
a documented itemized-bill request looks terrible to every regulator on the
escalation ladder — say so, politely, at rung 4.

## "The price is the price — that's what it costs."

> "Your own machine-readable standard-charges file lists your cash price
> for CPT [code] as $[X], and shows commercial insurers pay between $[Y]
> and $[Z]. I'm offering $[amount], which is above your Medicare rate.
> Who can approve that?"

The transparency file turns "the price" from a fact into an opening bid.

## "You already agreed to pay — you signed the financial responsibility form."

> "That form doesn't waive my right to dispute billing errors, my
> protections under the No Surprises Act, or my eligibility under your
> Financial Assistance Policy. I'm disputing specific charges, which I've
> itemized in writing."

## "You're already on a payment plan." / "You've already made payments."

Neither closes the door. Charity-care applications are generally open for
240 days after the first post-discharge bill regardless of payments made —
and approved applications can refund what was already paid. A payment plan
can be renegotiated when circumstances change; say the words "financial
hardship adjustment."

## "Your insurance already processed this — the balance is your responsibility."

Verify before accepting: bill ↔ EOB, line by line. If the provider's number
exceeds the EOB's "patient responsibility," that's the dispute. If the claim
was denied or paid out-of-network at an in-network facility, that's an
appeal or a No Surprises Act case, not a payment.

## "The facility fee is standard for all visits."

> "I'm asking you to waive or reduce the facility fee. I received routine
> outpatient care and was never told this clinic bills as a hospital
> department. Had I known, I'd have gone to an independent office."

Facility fees are among the most commonly waived charges — they're
discretionary revenue, several states restrict them, and hospitals know
they're indefensible for routine visits.

## "We only give discounts at the time of service."

> "Then treat this as time-of-service: I'm offering a one-time payment of
> $[X] within 15 days of written confirmation that it settles the account
> in full. That's faster and cheaper than collections recovery."

## "That's how the doctor coded it." (duplicate/upcoding dispute deflected)

The billing office treating the code as gospel is a routing problem — reps
can't change codes, but coding review can.

> "I understand you can't change the coding. Please route this account to
> coding review — I'm disputing CPT [code] as inconsistent with the
> documented care, and I'd like the review's outcome in writing. Until
> then the account is in dispute."

If coding review upholds it, the medical record is the referee: request it
(`records-request`) and compare the code's official description against
what's documented. "The doctor coded it" is not evidence; the chart is.

## "There's no discount for paying in full." (asked for prompt-pay, told no)

Front-line reps often can't see — or aren't incentivized to mention —
discount programs that financial counselors can apply. And "no discount"
coexists with a published cash price that's lower than what you're being
asked for.

> "Please transfer me to a financial counselor or billing supervisor. Your
> published standard-charges file lists a discounted cash price of $[X]
> for these services; I'd like to understand why paying in full today
> wouldn't qualify for at least that rate."

If it's genuinely a firm no, the evidence-based settlement offer in writing
is the next move — "no discount policy" collapses surprisingly often when
the alternative is a documented dispute.

## "We've billed your insurance — this balance is what's left."

Verify the sequence, not the assertion. Hospital statements routinely go
out before the claim has even been submitted (`inside-the-machine.md`).

> "On what date was the claim submitted to my insurance, and to which
> payer? I don't see a matching EOB. I won't be paying until I have the
> EOB showing patient responsibility, and I'd like the account held until
> then."

If the claim was never filed, was filed to the wrong payer, or was denied
for the provider's own coding/authorization error: the fix is the
provider's corrected resubmission, and a claim that missed the payer's
timely-filing deadline is generally the provider's write-off — not the
patient's bill.

## They just… never respond.

Silence is a tactic too. Every unanswered written request gets one follow-up
citing the first ("second request, first sent [date] by [method]"), then a
rung up the escalation ladder. Two ignored certified letters are exactly the
exhibit a state AG complaint wants.
