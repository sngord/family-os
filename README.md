# Family OS

**A world-class family assistant that runs in [Claude Code](https://claude.com/claude-code) or [Cursor](https://cursor.com) — powered by nothing but a folder of plain-text files.**

You do two small things:

1. **Dump thoughts into an inbox** the moment they cross your mind.
2. **Run one ~15-minute weekly review.**

Your assistant carries everything else: birthdays, registration deadlines, campsite booking windows, meal plans and grocery lists, date-night logistics, holiday prep. It hands you tight yes/no decisions instead of homework.

There's no app and no database. It's markdown files plus an operating manual (`CLAUDE.md`) that turns Claude Code into your family's Chief of Staff. Your data stays in this folder, on your machine.

---

## Quick start

1. **Install your agent** — [Claude Code](https://claude.com/claude-code) or [Cursor](https://cursor.com). Both are fully supported.
2. **Get this folder** — `git clone` this repo, or click **Code → Download ZIP** and unzip it anywhere.
3. **Open the folder in your agent** (Claude Code: run `claude` inside it or open it in the desktop app · Cursor: File → Open Folder, then open the Agent chat).
4. Type **`/setup`** (or just say *"set up my assistant"*). The very first question confirms which agent you're in, so every later step fits your tool.
5. Answer a short interview: name your assistant (and pick its avatar), choose capabilities, share family details, and optionally connect integrations like Google Calendar & Gmail — guided, with graceful fallbacks if you skip. 10–15 minutes, asked in small batches.

That's it. Your assistant builds its own memory files, renders your dashboard, and proposes your first weekly review.

## What it can manage

Pick any of these during setup — start small, add more later by saying *"enable ‹module›"*:

| Module | What you get |
|---|---|
| 📅 **Calendar & Email** | Reads/writes Google Calendar, scans Gmail for dates, RSVPs, and school emails (or exports one-click `.ics` files) |
| 🍝 **Meals & Groceries** | 2-week rotating menu + one aisle-grouped grocery list, ready to paste into Instacart |
| 💰 **Budget & Money** | Spending plan, bill calendar, subscription audits, sinking funds for holidays & camps |
| 💪 **Health & Fitness** | Workout blocks that survive busy weeks, league signups, family checkup cadences |
| ✅ **To-Dos & Projects** | One trusted list, triaged weekly, with big projects broken into next actions |
| 🎒 **Kids' Activities & Childcare** | Registration windows surfaced *before* they close; sitter roster; age-triggered unlocks |
| 🎪 **Local Events** | A weekly shortlist of things happening near you, tuned to your kids' ages |
| ⛺ **Outings & Travel** | Camping trips, day trips, vacations — planned end-to-end with booking lead times |
| 🎄 **Traditions & Celebrations** | Annual traditions, birthdays, and gifts prepped weeks ahead — every year, forever |
| ❤️ **Couple & 1:1 Time** | Date nights with sitter logistics handled; rotating one-on-one "kid dates" |
| 🔧 **Home & Maintenance** | Seasonal maintenance, filters and smoke alarms, vendor list, prep-for-winter checklists |
| 🌟 **Family Principles** | Draft your family's values over a few weeks, then make them visible in your home |

Full specs live in [`capabilities/`](capabilities/).

## The whole interface

| You do | Your assistant does |
|---|---|
| `/capture ‹thought›` (or edit `inbox.md`) | Parks it until the weekly review — nothing falls through |
| `/weekly-review` (~15 min, once a week) | Triages the inbox → surfaces deadlines whose prep window just opened → proposes the next 2 weeks → you reply with numbers |
| `/status` | One-screen dashboard: scheduled, pending, at risk of slipping |
| `/plan ‹thing›` | Fully plans a trip, party, or date night: options, a recommendation, bookings, calendar entries |
| `/meal-cycle` | Next 2 weeks of dinners + one consolidated grocery list |
| `/dashboard` | Re-renders your visual dashboard (see below) |
| `/connect` | Set up or test integrations (Google Calendar, Gmail, …) |
| *"do this now: …"* | Skips the inbox and acts immediately |

Slash commands ship for both agents (`.claude/commands/` and `.cursor/commands/`); if one ever doesn't appear in your tool, the plain phrases — "weekly review", "meal cycle", "status" — always work.

The magic is the **lead-time engine**: every recurring event stores *how far in advance prep must start* (campsites: months; summer camp: registration morning; Halloween costumes: 3 weeks). Each weekly review computes which prep windows just opened — so you're always ahead without tracking anything.

## The dashboard

Prefer a visual home base over chat and files? Open **`dashboard/dashboard.html`**
in any browser: your assistant's friendly avatar greets you on a home page with
what needs a decision, the next two weeks, and the health of every family pillar
— plus a page per capability showing upcoming plans, recent activity, and a
view-past drawer. Every button copies a ready-to-paste prompt, so the dashboard
and your agent stay one thought apart.

It's a single offline HTML file — no server, no accounts, nothing external.
Your assistant re-renders it after every weekly review (or on `/dashboard`),
and the rendered copy is gitignored like the rest of your personal data. Want a
peek right now? Double-click `dashboard/template.html` to tour it with a
fictional sample family, in light or dark mode.

## Your data & privacy

- Everything is local plain text. Nothing syncs anywhere unless you connect it.
- All personal files (`family/`, `systems/`, `logs/`, `plans/`, `inbox.md`, and your rendered dashboard) are **gitignored** — you can keep this folder as a git repo, pull template updates, even fork publicly, without ever committing family data.
- Calendar/email access is optional, via connectors you control, and the assistant confirms before creating events or sending anything.
- The assistant never handles passwords, card numbers, or money movement.

## Optional: connect Google Calendar & Gmail

Claude Code and Cursor each have their own path — [INTEGRATIONS.md](INTEGRATIONS.md) covers both (hosted connectors vs. `.cursor/mcp.json`), and setup walks you through whichever applies. No connector? The assistant generates `.ics` files you import into any calendar in one click.

## Make it yours

- Every file is editable — rename pillars, rewrite cadences, tune anything.
- Want a module that doesn't exist yet (aging parents, pets, homeschool)? Tell your assistant: *"draft a new capability module for X"* — it follows the format in [`capabilities/_template.md`](capabilities/_template.md).

## License

MIT — share it, remix it, gift it to another family.
