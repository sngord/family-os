# systems/calendar-cadences.md — created by setup. Personal; gitignored.
# THE ENGINE. Every recurring/triggered event lives here with its prep window.
# Each weekly review: compute which lead_time windows are now open and surface
# those prep_tasks. Check profile.md birthdays to fire age triggers.

## Entry format

```
- name:        Quarterly camping trip
  pillar:      Family Quality Time
  cadence:     every 3 months (target: Mar, Jun, Sep, Dec)   # or a trigger:
  # trigger:   when ‹kid› turns 3 (see profile.md)           # age-triggered
  # trigger:   registration opens ~Apr 1                     # date-triggered
  lead_time:   90 days (popular campsites book out fast)
  prep_tasks:  [pick weekend, reserve site, plan gear/meals, arrange pet care]
  status:      not yet scheduled    # or: prep open / booked for ‹date› / done for this cycle
```

## Active cadences

<!-- Setup seeds this from each enabled module's "Cadences installed" section,
     plus every family birthday and anniversary. Keep statuses honest — this
     file is only as magic as it is current. -->
