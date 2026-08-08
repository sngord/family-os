# SETUP.md — First-run interview

You (the assistant) run this when `family/config.md` doesn't exist, or when the
user says `/setup`. If config already exists, confirm before re-running — offer
to *update* specific answers instead of starting over.

## Ground rules for the interview

- Ask in **batches of at most 4 questions**. Use multiple choice or suggested
  defaults wherever possible — typing full sentences should feel optional.
- **"skip" is always a valid answer.** Note what was skipped so you can ask
  later when it becomes relevant.
- **Write files as you go** (after each phase), so progress survives an
  interruption. Track where you are in `family/setup-progress.md`; delete that
  file when setup completes.
- Keep the whole thing to **10–15 minutes**. Offer to pause anytime and resume
  later with `/setup`.
- Never re-ask something already answered. Never invent facts.
- Convert every relative date ("she turns 4 in March") to an absolute one.

---

## Phase 1 — Hello & a name

Open with 2–3 sentences: what this is (a family Chief of Staff living in this
folder), the two-habit promise (inbox + one weekly review), and that questions
come in short batches with skip always allowed.

Ask:
1. **What should we call your assistant?" Offer ~5 varied suggestions (e.g.,
   Jeeves, Marlo, Birdie, Atlas, Pip) plus "just 'Assistant' is fine."
2. What's your family name, or how should I refer to your household?
3. What city/area are you in? (Powers local suggestions — approximate is fine.)

## Phase 2 — The people

Explain in one line why you're asking: birthdays power age-triggered signups and
birthday planning; interests power ideas that actually land.

Batch A:
1. The adults: first names, and optionally what you each do for work + any fixed
   work-schedule facts (WFH days, travel, shift work).
2. The kids: first names, **exact birthdates**, and each kid's current
   obsessions/interests.
3. Pets? (They need care during trips.)

Batch B:
4. Weekly rhythm constraints: school/daycare hours, standing commitments,
   evenings that are always bad.
5. Budget comfort: a rough monthly number for "family fun + convenience," or
   "decide case by case."
6. Anything else I should never forget? (allergies, custody schedules, family
   nearby, religious/cultural observances — open door, fully optional)

→ Write `family/profile.md` (from `templates/profile.md`) now.

## Phase 3 — Choose capabilities

Show the menu below with numbers, each with its one-liner (pull from
`capabilities/README.md`). Recommend **starting with 3–5** — everything can be
enabled later with "enable ‹module›."

1. 📅 Calendar & Email
2. 🍝 Meals & Groceries
3. 💰 Budget & Money
4. 💪 Health & Fitness
5. ✅ To-Dos & Projects
6. 🎒 Kids' Activities & Childcare
7. 🎪 Local Events
8. ⛺ Outings & Travel
9. 🎄 Traditions & Celebrations
10. ❤️ Couple & 1:1 Time
11. 🔧 Home & Maintenance
12. 🌟 Family Principles

"Reply with numbers, e.g. `1 2 8`. Unsure? For most families I'd start with
1, 2, and 7 — calendar, meals, and weekend ideas — and add the rest later."

## Phase 4 — Module deep-dives

For each chosen module, open `capabilities/‹module›.md` and run its **Setup
questions** section, keeping the batching rules. Between modules, give a
one-line progress marker ("2 of 4 modules configured…").

If they chose 5+ modules, offer: "Want to configure the top 2 now and let the
rest ask their questions during your first weekly reviews instead?" (If yes,
mark deferred modules `pending-intake` in config — ask their questions
opportunistically later.)

## Phase 5 — Build the workspace

Create, using `templates/` for shapes:

- [ ] `family/config.md` — assistant name, family name, location, review day,
      `enabled_modules` list, pillars (default seven unless they customized).
- [ ] `family/profile.md` — done in Phase 2; add anything new.
- [ ] `family/vision.md` — stub: pillars listed, one seeded goal per pillar
      drawn from what you learned (mark all as drafts to refine together).
- [ ] `systems/calendar-cadences.md` — seed with: every enabled module's
      "Cadences installed" entries; each family birthday (annual, with a gift/
      party lead time); anniversaries or observances they mentioned.
- [ ] One `systems/‹module›.md` file per enabled module, per its spec.
- [ ] `inbox.md` — friendly 3-line header explaining capture.
- [ ] `logs/weekly-review.md` and `logs/decisions.md` — headers plus a first
      entry: "‹date›: Setup completed. Modules enabled: …"
- [ ] Delete `family/setup-progress.md`.

## Phase 6 — Graduation

1. Ask which day/time they want the weekly review (default: Sunday evening). If
   a calendar connector is live, offer to add a recurring reminder (confirm
   details first).
2. Print the card below (with their assistant's name), then offer a **5-minute
   mini first review** right now — usually there's already inbox material from
   the interview ("you mentioned wanting swim lessons — want me to look?").

```
🎉 ‹Name› is ready.

Your whole job from now on:
  1. Toss thoughts in   →  /capture ‹anything›     (or edit inbox.md)
  2. Once a week        →  /weekly-review          (~15 min, ‹day› ‹time›)

Anytime:  /status  ·  /plan ‹thing›  ·  /meal-cycle  ·  "do this now: …"
Add powers later: "enable ‹module›" — full list in capabilities/
```
