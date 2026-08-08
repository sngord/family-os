# 🍝 Meals & Groceries
> A two-week rotating dinner menu the family actually likes, and a grocery list
> ready to paste straight into your online order.

**Serves pillars:** Home & Logistics (and Health)
**Personal file:** `systems/meals.md`

## What your assistant does
- Maintains a **meal bank**: every dinner tagged with prep time, protein,
  kid-approved?, season, and make-ahead?.
- Arranges the bank into a **2-week rotation** you approve once; it then repeats
  with seasonal refreshes so nobody gets bored.
- On `/meal-cycle`, outputs the next 2 weeks of dinners plus **one consolidated,
  aisle-grouped grocery list** sized to your household — formatted to paste into
  Instacart/your store's site. (You place the order; the assistant never checks
  out for you.)
- Makes swaps trivial: "swap Tuesday week 2" → instant alternative + list delta.
- Introduces **one new recipe per cycle**, matched to your constraints, and
  retires flops without ceremony.
- Flags Sunday make-ahead batches and plans leftovers on your busiest nights.

## Setup questions
Batch 1:
1. How many dinners a week do you actually cook at home? (be honest)
2. Weeknight cooking budget: 15, 30, or 45 minutes?
3. Dietary rules and allergies — hard rules vs. preferences.
4. Kid realities: what do they reliably eat? What's banned by popular veto?

Batch 2:
5. Proteins/cuisines you love; anything you're sick of.
6. How do groceries happen — Instacart, store pickup, in-store? Which store?
7. Rough weekly grocery budget, if you track one.
8. Just dinners, or should I also handle breakfast/lunch staples on the list?

## Files
- `systems/meals.md` — meal bank, current rotation, pantry staples checklist,
  new-recipe queue, retired list.

## Cadences installed
- Meal cycle — every 2 weeks; lead_time: 3 days before groceries are needed;
  prep_tasks: [confirm menu, output grocery list, family places order].
- Rotation refresh — quarterly (seasonal produce + boredom check).

## Commands
- `/meal-cycle` → next 2 weeks + consolidated list.
- "swap ‹day› ‹week›" → replacement meal + list adjustments.
- "add ‹meal› to the bank" → tagged and queued into rotation.

## The world-class bar
- The list is one paste, grouped by aisle, with quantities right for your
  family size — no editing needed.
- Theme nights (taco Tuesday-style) cut decisions; the rotation absorbs busy
  nights with make-aheads instead of collapsing into takeout guilt.
- New recipes appear at a rate of exactly one per cycle: novelty without risk.
