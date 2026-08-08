# INTEGRATIONS.md — connecting your tools

Family OS works fully offline with plain files. Integrations make it *magic* —
but every one is optional, and every one has a graceful fallback. The setup
interview walks through this once; revisit anytime with **`/connect`**.

The assistant's rules, regardless of integration:
- It never sees or stores passwords — connections use each service's own
  sign-in (OAuth), handled by Claude Code, revocable by you anytime.
- It confirms before writing to a calendar or drafting anything.
- It never sends email, moves money, or submits forms on its own.

## How connecting works in Claude Code

Integrations are **connectors** (MCP servers) added to Claude Code:

- **Desktop app:** Settings → Connectors (or Extensions) → add Google
  Calendar / Gmail / others → approve the sign-in in your browser.
- **CLI:** `claude mcp add ‹name›` — or a project `.mcp.json` for advanced
  setups.
- Menus move between versions — if you can't find it, just ask your
  assistant: *"walk me through connecting Google Calendar"* and it will guide
  you against the current docs.

After connecting, tell your assistant to **test it** — it will do a harmless
read (list calendars, count unread threads) and record the result in
`family/config.md` so every future session knows what's available.

## The roster

| Integration | What it unlocks | Without it (fallback) |
|---|---|---|
| **Google Calendar** | Assistant reads your real schedule and writes approved events, recurrences, and prep reminders directly | Assistant generates `.ics` files in `plans/` — you import with one click |
| **Gmail** | Sweeps for buried dates: school newsletters, signups, RSVPs, confirmations; drafts replies on request | You forward/paste anything important into `inbox.md` |
| **Web search / browsing** | Live research: local events, campsite availability, league registration dates, venue details | Assistant tells you exactly what to look up and drafts the query |
| **Google Drive** | Reads/writes shared family docs (school forms, packing lists you keep there) | Files live in this folder instead |
| **Grocery (Instacart etc.)** | Usually **no connector needed** — the meal module outputs a paste-ready list; you stay in control of the cart | That *is* the design |
| **Anything else** | Claude Code has a growing connector directory (task apps, notes, smart home). If it helps a module, your assistant can check whether a trusted connector exists | Ask: *"is there a connector for ‹X›?"* |

**A note on trust:** only add connectors from sources you trust — they act
with your accounts' permissions. When in doubt, skip it; the fallbacks are
genuinely fine.

## What gets recorded

`family/config.md` keeps a simple ledger the assistant maintains:

```
integrations:
  google_calendar: connected     # tested 2026-08-09 · calendar "Family"
  gmail: fallback                # user prefers forwarding to inbox
  web_search: connected
```

States: `connected` · `fallback` (declined, use the fallback) · `pending`
(wants it, not yet set up — the assistant offers help at the next review).
