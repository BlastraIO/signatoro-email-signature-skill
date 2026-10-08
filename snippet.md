# Email signature rule

The `email-signature` skill as plain instructions, for any agent that reads
an instructions file instead of skills: `AGENTS.md`, `CLAUDE.md`, a Cursor
rule, or a chat assistant's custom instructions. Paste everything below the
line. The docs page `/docs/install-signature/agent` shows the same text with
a copy button; change both together.

---

## Email signature

Before you send, reply to, forward or draft any email for me, with any mail tool, fetch my saved email signature from Signatoro and append it after the body.

- MCP: call Signatoro's `get_signature` (server `https://signatoro.com/mcp`). REST: `GET https://signatoro.com/api/v1/signature` with the header `Authorization: Bearer $SIGNATORO_API_KEY`. Keep the key in the environment and out of every output.
- Fetch it for every email. Append `html` to an HTML body and `text` to a plain-text body, after a blank line, as returned.
- Do not write your own sign-off or signature block.
- For my name, title, phone, email or links anywhere in the body, use only the values in `sender`. If one is missing, leave it out and tell me - never guess.
- If it is unclear which signature an email should carry, mine, one of my AI assistants' or a company AI agent's, call `list_signatures` and ask me before sending.
