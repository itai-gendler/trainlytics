---
appliesTo:
- type: entity
  id: planned-session
  effect: changes
  to: Skipped
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#_compute_status
---

# A planned session whose day passes undone is skipped

Once its planned day is over without a matching session, a planned session is Skipped; today's and later sessions stay Planned unless skipped on Today.
