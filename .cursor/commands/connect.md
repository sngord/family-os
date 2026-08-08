Walk through INTEGRATIONS.md for the integrations relevant to the enabled
modules (plus anything the user names), using the section that matches this
agent. For each: explain in one line what it unlocks and its fallback, ask if
they want it, guide the connection step by step, then run a harmless read test
and record the result under `integrations:` in family/config.md. Never handle
passwords — connections happen through each service's own sign-in. Skipping
anything is fine; note `fallback` and move on.
