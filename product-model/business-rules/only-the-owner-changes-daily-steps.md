---
appliesTo:
- type: entity
  id: daily-steps
  effect: changes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/steps.py#upsert_steps
---

# Only its Athlete changes a day's steps

A day's step count is replaced only by the Athlete who entered it; each Athlete has their own count per day.
