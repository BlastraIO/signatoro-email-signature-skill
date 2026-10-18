# Email signature skill

One email signature for humans and AI agents.

Signatoro is the agentic email signature platform: save your signature once, and your people and every AI agent you connect use the same one.

An [Agent Skill](https://agentskills.io/specification) that makes an AI agent
fetch the user's saved email signature from Signatoro and append it to every
email it sends, replies to, forwards or drafts. The agent picks it up when it
is about to send mail, whether or not the user mentions a signature.

- `email-signature/SKILL.md` - the skill, for agents that load skills
  (Claude Code, Codex, Cursor).
- `snippet.md` - the same rule as plain text, for `AGENTS.md`, `CLAUDE.md`, a
  Cursor rule or a chat assistant's custom instructions.

Every agent you use or switch to - Claude Code, Codex, Cursor, OpenClaw or
your own - fetches the same saved signature, so one edit on Signatoro
reaches all of them, and each agent can sign with a signature of its own.
Signatoro is free to start, and every plan includes the MCP server and API.

The wording mirrors the Signatoro MCP server's own instructions.
Docs: https://signatoro.com/docs/install-signature/agent

## Before installing: connect Signatoro

The skill needs one of these:

- **MCP:** add the Signatoro server, `https://signatoro.com/mcp`, to the
  agent. It signs in through the browser.
- **REST:** on the [signature page](https://signatoro.com/home), under "For
  tools and assistants", click "Generate API key", and put the key in the
  agent's environment as `SIGNATORO_API_KEY`.

## Install

With the [skills CLI](https://skills.sh), for any agent it supports:

```bash
npx skills add BlastraIO/signatoro-email-signature-skill
```

Or copy the `email-signature` folder (the folder, with `SKILL.md` inside it) to
one of these places.

### Claude Code

- All your projects: `~/.claude/skills/email-signature/`
- One project: `.claude/skills/email-signature/` in the repository

Or paste `snippet.md` into `CLAUDE.md`.

### Codex

- All your projects: `~/.agents/skills/email-signature/`
- One project: `.agents/skills/email-signature/` in the repository

Or paste `snippet.md` into `AGENTS.md`: `~/.codex/AGENTS.md` for every
project, or `AGENTS.md` at the repository root for one.

### Cursor

- All your projects: `~/.cursor/skills/email-signature/` or
  `~/.agents/skills/email-signature/`
- One project: `.cursor/skills/email-signature/` or
  `.agents/skills/email-signature/` in the repository

Or paste `snippet.md` into `AGENTS.md` at the project root, or into a project
rule, `.cursor/rules/email-signature.mdc`:

```markdown
---
description: Sending, replying to, forwarding or drafting an email
alwaysApply: false
---

(the rule text from snippet.md)
```

### OpenClaw

- All your agents: `~/.openclaw/skills/email-signature/`
- One workspace: `skills/email-signature/` in the workspace

Set `SIGNATORO_API_KEY` in the agent's environment. Give each agent its own
key, made for that agent on Signatoro, and each one signs as itself.

## License

MIT

## Sources

Checked on 2026-10-08:

- [Agent Skills specification](https://agentskills.io/specification)
- [Claude Code: skills](https://code.claude.com/docs/en/skills)
- [Codex: skills](https://developers.openai.com/codex/skills) and
  [AGENTS.md](https://developers.openai.com/codex/guides/agents-md)
- [Cursor: skills](https://cursor.com/docs/skills) and
  [rules](https://cursor.com/docs/context/rules)
