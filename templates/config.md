# family/config.md — created by setup. Personal; gitignored.
# The assistant reads this at boot. CLAUDE.md itself is never personalized.

agent:               # claude-code | cursor | other — asked at Phase 0
assistant_name:
family_name:
location:            # city/area — used for local research, never full address
review_day:          # e.g., Sunday 7:30pm

avatar:              # the assistant's dashboard face
  style:             # classic | sprout | spark | bow | glasses
  color:             # blue | aqua | violet | magenta | orange — or any hex

integrations:        # connected | fallback | pending (see INTEGRATIONS.md)
  google_calendar:
  gmail:
  web_search:

enabled_modules:
  # exact filenames from capabilities/, without .md — e.g.:
  # - calendar-email
  # - meals-groceries

pending_intake:      # modules enabled but whose setup questions are deferred
  # - budget-money

pillars:             # edit freely; these define "thriving" for this family
  - Couple & Partnership
  - Family Quality Time
  - 1:1 Parent–Child Time
  - Health & Fitness
  - Traditions & Rituals
  - Principles & Character
  - Home & Logistics

setup_completed:     # YYYY-MM-DD
