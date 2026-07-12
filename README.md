# FairBill

**Turn your AI agent into a medical-bill negotiation advocate.**

Point Claude Code (or any coding agent that reads `AGENTS.md`) at this repo,
show it your medical bill, and it will run the same playbook professional
patient advocates and former billing insiders use: get the itemized bill,
audit it for errors, benchmark every charge against Medicare rates and the
hospital's own published prices, screen for charity care the hospital is
legally required to offer, and negotiate — by email, by formal letter sent
certified mail, and by phone scripts it preps for you.

Medical billing runs on information asymmetry. Hospitals know that billed
charges are opening numbers (often 3–10x what insurers actually pay), that
roughly half of itemized bills contain errors, that nonprofit hospitals are
required by federal law to have financial assistance policies most patients
never hear about, and that almost nobody appeals insurance denials even
though appeals frequently succeed. Billers know the rules. Now your agent
does too. **The goal: you pay what is fair — nothing more.**

## Quickstart

```bash
git clone https://github.com/YOURNAME/fairbill
cd fairbill
claude   # or any agent that reads AGENTS.md
```

Then just say:

> I got a bill from the hospital and I think it's too high. Help.

The agent will open a case file, ask for the bill (drop the PDF or a photo
into the case folder — it can read both), and take it from there. Your case
files live in `cases/`, which is **gitignored — your medical information
never leaves your machine.**

Works best with an email connector (e.g. the Gmail MCP connector in Claude
Code) so the agent can prepare drafts in your account — but it degrades
gracefully to copy-paste drafts without one.

## What the agent actually does

| Phase | What happens |
|---|---|
| **Prevention** | For upcoming care: the four questions that stop bad bills before they exist, Good Faith Estimates, what's really in the admissions paperwork |
| **Intake** | Reads your bill/EOB/collection letters, builds a private case file, triages deadlines |
| **Evidence** | Demands the itemized bill with CPT codes, audits it against a known-error checklist, pulls Medicare rates and the hospital's own price-transparency file |
| **Rights screen** | Charity care (IRS 501(r)), No Surprises Act, Good Faith Estimate disputes, insurance appeals, debt-validation deadlines |
| **Strategy** | Picks the play, sets a documented fair-price target, writes the game plan for your sign-off |
| **Execution** | Drafts every email and letter (you approve before anything is sent), walks certified mail through an online service or USPS, and preps a one-page brief before every phone call you make |
| **Paper trail** | Logs every call, recaps every promise in writing, tracks every deadline |

## What this is not

- **Not legal, medical, or financial advice.** It's general information and
  drafting help. Lawsuits, garnishment, bankruptcy → get a lawyer
  (lawhelp.org has free legal aid directories).
- **Not autonomous.** The agent never sends a message, files a complaint, or
  offers a number without your explicit approval. You stay the negotiator;
  it's your staff.
- **Not a debt-relief company.** Nothing here charges you, takes a cut, or
  touches your money.
- **US-focused.** The laws and benchmarks are American. PRs adapting the
  playbook elsewhere are welcome.

## Repo map

```
AGENTS.md            ← the agent's operating manual (start here)
CLAUDE.md            ← Claude Code specifics
.claude/skills/      ← 10 skills: intake, review-bill, benchmark-price,
                       financial-assistance, strategy, draft-email,
                       send-letter, phone-prep, collections, insurance-appeal
knowledge/           ← tactics, laws & rights, price benchmarks, glossary,
                       objection handling, prevention (before-care),
                       how billing works from the inside
templates/           ← letters (certified-mail grade) and emails
cases/               ← YOUR case files (gitignored, private)
```

Humans are welcome to read everything in `knowledge/` and `templates/`
directly — it's a useful playbook even without an agent.

## Results to expect

Negotiated reductions of 30–60% are routine when backed by evidence;
charity-care approvals can wipe bills entirely; billing-error disputes and
No Surprises Act violations often knock out whole line items. None of it is
guaranteed — what's guaranteed is that paying the first number without
checking is the worst move available.

## Contributing

The playbook gets stronger with every negotiation. Share the tactic that
worked, the objection you heard and the comeback that beat it, your state's
charity-care law — **never your personal details**. See
[CONTRIBUTING.md](CONTRIBUTING.md).

## Credits & further reading

This project stands on the work of people who've been fighting the
asymmetry publicly for years: patient advocates like
[Dollar For](https://dollarfor.org) (free charity-care help),
Marshall Allen's book *Never Pay the First Bill*, billing-insider educators
on social media such as [@milarowannn](https://www.instagram.com/milarowannn/),
and the public resources at [cms.gov/medical-bill-rights](https://www.cms.gov/medical-bill-rights)
and the CFPB. If a bill is crushing you and you want humans in the loop,
[claims.org](https://www.claims.org) lists professional patient advocates.

## License

[MIT](LICENSE). Free to use, fork, and build on — commercially too.
