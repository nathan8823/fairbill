---
name: draft-email
description: Draft and (with approval) send negotiation emails through the user's email account. Use for itemized-bill requests, dispute follow-ups, call recaps, and settlement correspondence.
---

# Draft email

## Capability check (once per session)

Use whatever email tooling exists — Gmail/Outlook MCP connector, `himalaya`,
Apple Mail via computer use, anything the user has wired up. **Preferred
mode: create a draft in their account and have them hit send.** If no email
tool exists: write the draft to `cases/<case>/letters/` as
`email-yyyy-mm-dd-<topic>.md` with To/Subject/Body clearly marked for
copy-paste, and offer to help set up the Gmail MCP connector for next time.

## Non-negotiables

- **Never send without the user seeing the exact final text, recipient, and
  subject, and approving.** One approval = one email. "Send it" in a prior
  session is not approval for this one.
- Find the right address first: billing-department email from the bill or
  provider site. Avoid generic contact forms when a real mailbox exists —
  forms don't leave the user a copy.
- Subject line formula: `Account #<number> — WRITTEN DISPUTE: <topic>` (or
  REQUEST). The account number makes it land in the right queue; the word
  "dispute" starts the paper trail.

## Structure that works

1. One line of who/what: patient name, account number, date of service.
2. The ask, stated in the first three lines. Not the story — the ask.
3. Numbered facts, each anchored to a document ("your itemized statement
   dated…", "your published standard-charges file lists…", "per our call
   with Maria on 7/2, ref #48119…").
4. The specific action requested + a response deadline (10–15 business
   days), and "please respond in writing."
5. "This account is in dispute" when applicable — and a line noting the
   dispute should be recorded on the account.

Tone per AGENTS.md: firm, factual, boring. No emotion in the email; keep
that for the user. Templates in `templates/emails/`; personalize fully — a
placeholder left in ruins credibility.

## After sending

Log to `case.md` (date, recipient, subject, deadline set). Calendar the
follow-up: no reply by deadline → one follow-up citing the first, then up
the escalation ladder.
