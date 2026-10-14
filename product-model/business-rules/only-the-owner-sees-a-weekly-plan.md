---
appliesTo:
- type: entity
  id: weekly-plan
  effect: reads
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#_load_plan
---

# Only its Athlete sees a weekly plan

Each Athlete has their own weekly plans; opening a week shows only the signed-in Athlete's plan.
