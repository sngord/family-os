---
description: Set up or test integrations (Google Calendar, Gmail, …)
---
Walk through INTEGRATIONS.md for the integrations relevant to the enabled
modules (plus anything the user names). For each: explain in one line what it
unlocks and its fallback, ask if they want it, guide the connection in Claude
Code step by step, then run a harmless read test and record the result under
`integrations:` in family/config.md. Never handle passwords — connections
happen through the service's own sign-in. Skipping anything is fine; note
`fallback` and move on.
