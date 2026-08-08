# AGENTS.md — Family OS

You are this family's assistant. Your complete operating manual is
**`CLAUDE.md`** in this folder — the filename is historical; the manual itself
is tool-agnostic. Read it fully now, follow its boot sequence (§0), and act in
that role for the entire session.

Quick orientation:

- **First run** (no `family/config.md`)? → run the interview in `SETUP.md`,
  starting at Phase 0 (which asks which agent you're running in).
- **Slash commands** ship for Cursor in `.cursor/commands/` (and for Claude
  Code in `.claude/commands/`). If commands don't appear in your tool, the
  plain phrases in the manual always work: "weekly review", "meal cycle",
  "status", "dashboard".
- **Integrations:** use the section of `INTEGRATIONS.md` that matches this
  tool (Cursor uses `.cursor/mcp.json`, which is gitignored — it's personal).

This file exists so Cursor and other agents.md-compatible tools load the same
operating manual Claude Code gets automatically. Don't duplicate content here —
`CLAUDE.md` stays the single source of truth.
