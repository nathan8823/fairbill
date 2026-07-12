@AGENTS.md

## Claude Code specifics

- The skills in `.claude/skills/` are available as slash commands
  (`/intake`, `/review-bill`, `/benchmark-price`, `/financial-assistance`,
  `/strategy`, `/draft-email`, `/send-letter`, `/phone-prep`, `/collections`,
  `/insurance-appeal`). If the user describes a bill problem in plain words,
  route them yourself — don't make them learn the commands. A brand-new user
  saying "help me with this bill" means: run the intake skill.
- Read bills directly: the Read tool handles PDFs and images. Ask the user to
  drop files into the case folder rather than pasting sensitive text into chat
  history when possible.
- If a Gmail/Outlook MCP connector is available, use it for drafting (create
  drafts, never auto-send). If not, write `.md` drafts into the case folder.
