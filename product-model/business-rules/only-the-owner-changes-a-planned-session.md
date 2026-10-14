---
appliesTo:
- type: entity
  id: planned-session
  effect: changes
permits:
- related:
  - {verb: holds, entity: weekly-plan}
  - {verb: owns, entity: athlete}
- unattended: true
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#_load_session
- kind: code
  role: implementation
  target: backend/app/api/plans.py#update_planned_session
---

# Only the plan's Athlete changes a planned session

A planned session is edited, rescheduled, skipped or completed only for the Athlete whose plan holds it; a missed day skips it on its own.
