# 📅 Calendar & Email
> The backbone: your assistant reads and writes the family calendar and mines
> email for the dates hiding inside it.

**Serves pillars:** all — this is the delivery mechanism for everything else
**Personal file:** `systems/calendar.md`

## What your assistant does
- Creates, updates, and deletes Google Calendar events — always showing details
  and getting a yes first, batching a week's approvals into one action.
- Puts logistics *in* the event: address, confirmation numbers, what to bring,
  who's got the kids.
- Adds prep tasks as their own earlier reminders (not just the event date).
- Scans email on a set rhythm for buried dates: school newsletters, activity
  signups, RSVPs, appointment confirmations — and routes them to the inbox or
  calendar. Never sends or replies on its own; drafts only, on request.
- Opens every weekly review with a clean agenda of the next two weeks, conflicts
  flagged.
- **No connector? No problem.** Generates `.ics` files in `plans/` for approved
  events — a one-click import into Google/Apple/Outlook calendars.

## Setup questions
Batch 1:
1. Is a Google Calendar connector set up in Claude Code? (If yes, I'll list your
   calendars to test. If no, I'll use `.ics` files — or help you connect one.)
2. Which calendar is the family's "source of truth"? Any others I should read
   (work, partner's, school feed)?
3. Do you two share a calendar, or should family events go somewhere specific?

Batch 2 (email — optional):
4. Want me to sweep email for dates? How often — with each weekly review, or a
   quick daily skim?
5. Which senders actually matter? (school, daycare, coaches, teams, doctor's
   offices — names/domains)
6. Ground rule confirm: I never send email myself; I only draft when you ask.

## Files
- `systems/calendar.md` — connector status, calendar names/roles, email-sweep
  rules, senders that matter, standing event conventions.

## Cadences installed
- Weekly agenda preview — part of the weekly review (no lead time).
- Email sweep — at chosen frequency; prep_task: route found dates to inbox.

## Commands
- "add to calendar: …" → structured event proposal → confirm → write.
- "what's coming up?" → two-week agenda with conflicts and gaps.

## The world-class bar
- An event isn't real until it's on the calendar with logistics inside it.
- The family never discovers a school event the night before — the sweep caught
  it two weeks ago and the weekly review already handled it.
- Zero unapproved writes, ever. Trust is the product.
