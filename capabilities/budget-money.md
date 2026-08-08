# 💰 Budget & Money
> A calm monthly money rhythm: bills never surprise you, subscriptions get
> audited, and December is funded by September.

**Serves pillars:** Home & Logistics
**Personal file:** `systems/money.md`

**Hard guardrails:** your assistant never sees credentials, never logs into
financial accounts, never moves money, and doesn't give investment advice. It's
a planning clerk working from numbers *you* provide.

## What your assistant does
- Maintains a **bill calendar**: every recurring bill with amount, due date, and
  a reminder lead time — wired into the lead-time engine.
- Runs a **15-minute monthly money review**: what's due, what changed, what's
  ahead (annual insurance, registrations, camp deposits).
- Tracks **sinking funds** for lumpy expenses — holidays, summer camp, vacation,
  car maintenance — so big months are pre-funded in small pieces.
- **Quarterly subscription audit**: lists everything recurring and asks "still
  worth it?" line by line.
- Prices its own plans: every outing, party, or trip the assistant proposes in
  other modules carries a cost estimate checked against your comfort number.
- Optional: tracks kid allowances/chore money.

## Setup questions
Batch 1:
1. How should money data get in? (a) you tell me numbers as they come up,
   (b) you drop bank/card CSV exports into `systems/money/` monthly for me to
   summarize, (c) bills-only — just keep me from missing due dates.
2. List your recurring bills + rough amounts + due days (start with the big
   ones; we'll grow it).
3. Monthly comfort number for family fun/convenience spending (may already be
   in your profile — confirm).

Batch 2:
4. Which lumpy expenses bite you each year? (holidays, camps, insurance,
   property tax…) Want sinking funds for them?
5. Subscription audit: want it quarterly, or only when asked?
6. Kid allowances to track?

## Files
- `systems/money.md` — bill calendar, sinking funds ledger, subscription list,
  comfort numbers. (CSV drops, if used, live in `systems/money/` — all
  gitignored with the rest of your personal data.)

## Cadences installed
- Monthly money review — monthly; lead_time: none; 15 minutes.
- Subscription audit — quarterly.
- Holiday sinking fund check — monthly Sep–Dec; lead_time: starts in September.
- One entry per big annual bill — lead_time: 3 weeks before due.

## Commands
- "money review" → the monthly rundown, decision-shaped.
- "can we afford ‹X›?" → honest math against comfort numbers and sinking funds.

## The world-class bar
- No bill is ever a surprise; no subscription survives unexamined past 90 days.
- Holiday spending is boring by December because it started in September.
- Every plan in every other module arrives pre-priced.
