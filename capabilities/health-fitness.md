# 💪 Health & Fitness
> Workouts that survive busy weeks, and a family whose checkups, refills, and
> signups are never overdue.

**Serves pillars:** Health & Fitness
**Personal file:** `systems/health.md`

**Note:** your assistant schedules and remembers; it doesn't give medical
advice. It stores only the health info you choose to give it, locally.

## What your assistant does
- Schedules your workouts as **calendar blocks treated like meetings** — when
  life collides, they get *moved*, not deleted.
- Tracks adult fitness commitments (gym, classes, leagues) including league
  **registration windows** via the lead-time engine.
- Maintains the family **checkup cadence**: dentist every 6 months, annual
  physicals, eye exams, pediatric well-visits — per person, with booking lead
  times (good pediatric dentists book out weeks ahead).
- Reminds on prescription refills and immunization timing if you track them.
- Reports habit streaks in the weekly review with **honesty and zero nagging** —
  one line, no guilt.
- Suggests seasonal family movement: hikes, bike days, pool sessions — matched
  to kids' ages and the weather.

## Setup questions
Batch 1:
1. Your fitness goal right now, in one line. And your partner's, if they want in.
2. Realistic workout slots per week, and when? (e.g., "MWF 6am" or "2 evenings")
3. Gym, home, or outdoors? Any league/class you're in or want to join?

Batch 2:
4. Family checkup status — roughly when was each person's last dentist /
   physical / eye exam? ("no idea" is a fine answer; we'll reset the clocks.)
5. Who's the pediatrician/dentist? (names only — so reminders can say "book
   with Dr. ‹X›")
6. Any refills or recurring health tasks to track? (optional, fully skippable)

## Files
- `systems/health.md` — workout schedule, league windows, per-person checkup
  ledger (last visit → next due), providers, tracked habits.

## Cadences installed
- Workout blocks — weekly recurrence per stated slots.
- Dentist per person — every 6 months; lead_time: 3 weeks to book.
- Annual physical / well-child visit per person — annual; lead_time: 4 weeks.
- League registration — per league; lead_time: set from that league's real
  window when researched.

## Commands
- "reschedule my workout" → moves the block, keeps the week's count honest.
- "health status" → per-person overdue/upcoming table.

## The world-class bar
- Six months from setup, nobody in the family is overdue for anything — and
  nobody had to remember it.
- Missed workouts trigger rescheduling, not shame.
