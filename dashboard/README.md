# Dashboard — generation spec

The visual interface for Family OS. One self-contained HTML app, no server, no
build step, works offline.

- **`template.html`** — the generic app, shipped with fictional sample data.
  Double-click it anytime for a preview. Never personalized; safe to commit.
- **`dashboard.html`** — the family's real dashboard, rendered by the
  assistant. Contains personal data → **gitignored**.

## How the assistant renders it (`/dashboard`)

1. Read `template.html`.
2. Build the data object per the schema below from the family's current files:
   `family/config.md` + `profile.md` (identity, avatar), `inbox.md` (count),
   `systems/calendar-cadences.md` (open prep windows → *needs_attention*,
   upcoming events → *up_next*), each enabled module's `systems/` file
   (stats, upcoming, details), `logs/weekly-review.md` + `logs/decisions.md`
   (recent + history), and the latest pillar check.
3. Replace everything between `/*FAMILY-OS-DATA-START*/` and
   `/*FAMILY-OS-DATA-END*/` with a comment line and one statement:
   `window.FAMILY_OS_DATA = { …valid JSON… };`
4. Write the result to `dashboard/dashboard.html`. Tell the family to open it
   (or just refresh the browser tab if it's already open).

**Regenerate silently after every weekly review** and after any command that
changes plans (a booking, a new plan, an enabled module). Keep `generated`
fresh so staleness is visible.

## Rules

- `demo` must be `false` in the rendered file (it hides the sample banner).
- All values are **plain text** — the app escapes HTML, so never embed markup.
- Dates are display-ready strings ("Sat · Aug 9", "by Aug 15") — write them the
  way a person would say them; keep lists sorted soonest-first.
- Be honest: only include what's actually in the files. An empty array renders a
  friendly empty state — that's better than invented content.
- Bound the payload: ≤ 8 `up_next`, ≤ 5 `needs_attention`, ≤ 6 per module
  `upcoming`/`recent`, ≤ 10 per module `history`, ≤ 8 home `recent`.
- Every `prompt` string must be something the family can paste into their
  agent as-is (a slash command or a natural phrase the assistant understands).
- Set `agent` to the display label matching config (`"Claude Code"` or
  `"Cursor"`) — the UI uses it in its "paste into …" copy.

## Schema

```jsonc
{
  "demo": false,
  "generated": "Sunday, Aug 9 · 8:02 PM",       // when this render happened
  "agent": "Claude Code",                        // display label from config `agent:` —
                                                 // "Claude Code" or "Cursor"; used in UI copy
  "assistant": {
    "name": "…",                                 // from family/config.md
    "tagline": "Your family's chief of staff",
    "avatar": {
      "style": "classic|sprout|spark|bow|glasses",
      "color": "blue|aqua|violet|magenta|orange" // or any hex like "#7a4de0"
    }
  },
  "family_name": "…",
  "next_review": "Sunday · 7:30 PM",
  "inbox_count": 0,                              // items currently in inbox.md
  "quick_actions": [ { "label": "…", "prompt": "…" } ],   // 2–3, review first
  "home": {
    "headline": "one-line pulse of the week",    // optional
    "needs_attention": [{                        // open lead-time windows & deadlines
      "severity": "warning|serious",             // serious = time-sensitive now
      "title": "…", "deadline": "…", "action": "what the assistant already prepared",
      "prompt": "…"                              // optional paste-ready follow-up
    }],
    "up_next": [{ "date": "…", "title": "…", "module": "short tag", "detail": "…" }],
    "pillars": [{ "name": "…", "status": "healthy|quiet|attention", "note": "…" }],
    "recent": [{ "date": "…", "text": "…" }]
  },
  "modules": [{                                  // one per ENABLED module, nav order
    "id": "meals-groceries",                     // must match capabilities/ filename
    "emoji": "🍝", "name": "Meals & Groceries",
    "status_line": "one-line current state",
    "stats": [{ "value": "…", "label": "…", "sub": "…" }],        // ≤ 4 tiles
    "upcoming": [{ "date": "…", "title": "…", "detail": "…" }],
    "recent":   [{ "date": "…", "title": "…", "detail": "…" }],
    "history":  [{ "date": "…", "title": "…", "detail": "…" }],   // the "view past" drawer
    "details": [{ "k": "…", "v": "…" }],         // standing facts, not events
    "actions": [{ "label": "…", "prompt": "…" }] // ≤ 3, most-used first
  }],
  "available_modules": [{                        // NOT-yet-enabled → "Add capabilities" page
    "id": "…", "emoji": "…", "name": "…", "blurb": "one enticing line"
  }]
}
```

## Design notes (for anyone editing the template)

- Colors follow the token block at the top of `template.html`; status colors
  (good/warning/serious) always appear **with a text label**, never alone.
- Dark/light both supported: OS preference by default, in-app toggle wins.
- The accent color and avatar come from config; the five named presets are
  contrast-tuned per theme. No external fonts, scripts, or images — the file
  must stay fully self-contained and offline.
