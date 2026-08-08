# 🎒 Kids' Activities & Childcare
> Registration windows surfaced before they close, a sitter you can book
> tonight, and activities that unlock automatically as kids hit the right age.

**Serves pillars:** Health & Fitness, 1:1 & Family time (via reliable childcare)
**Personal file:** `systems/childcare.md`

## What your assistant does
- Maintains a **signup tracker** for swim / sports / camps / classes with each
  program's real registration window wired into the lead-time engine — surfaced
  *before* it opens, with a calendar block at opening time for the competitive
  ones (popular swim slots and summer camps go in minutes).
- Fires **age-triggered unlocks** from birthdays in `family/profile.md`:
  "‹Kid› turns 4 in March — that unlocks pre-K soccer and swim level 2; want me
  to research options?"
- Keeps the **sitter/nanny roster**: names, contact, rates, which kids they
  know, last used — so "book a sitter for the 14th" is one message.
- Tracks daycare/aftercare searches when active: shortlist, waitlist status,
  cost, commute.
- Watches **activity load** per kid per season and says so when a schedule
  looks like it belongs to a tiny CEO.
- Previews each season 6 weeks out: what's ending, what's next, what needs
  registering.

## Setup questions
Batch 1:
1. Per kid: current activities (with days/times), and their dream list.
2. Any registration window that's burned you before? (I'll make it structurally
   impossible to miss again.)
3. Comfortable activity load: how many activities per kid per season?

Batch 2:
4. Childcare situation: daycare / school + aftercare / home? Anything you're
   searching for right now?
5. Sitters you already use: names, contact, rates. None? I'll help you build a
   roster (asking friends, local groups, sitter sites — you make the contacts).
6. What's the backup plan for sick days, and should I help design one?

## Files
- `systems/childcare.md` — signup tracker, sitter roster, daycare search state,
  per-kid activity load, backup-care plan.

## Cadences installed
- One entry per known registration window — lead_time: 2 weeks before opening.
- Season preview — 6 weeks before each season change.
- Age triggers — from each kid's birthday (checked every weekly review).
- Sitter roster refresh — twice a year.

## Commands
- "book a sitter for ‹date›" → roster shortlist + drafted message for you to send.
- "what can ‹kid› start now?" → age-eligible options with a recommendation.

## The world-class bar
- No missed registration, ever again. The window opens; you were ready last week.
- Sitter booking takes one message because the roster is warm and current.
- Kids' schedules serve the kids — the assistant defends white space too.
