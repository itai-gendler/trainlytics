---
appliesTo:
- type: entity
  id: planned-session
  effect: removes
permits:
- related:
  - {verb: holds, entity: weekly-plan}
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#delete_planned_session
---

# Only the plan's Athlete deletes a planned session

A planned session is deleted only by the Athlete whose plan holds it.
