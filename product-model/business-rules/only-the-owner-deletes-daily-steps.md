---
appliesTo:
- type: entity
  id: daily-steps
  effect: removes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/steps.py#delete_steps
---

# Only its Athlete deletes a day's steps

A day's step count is deleted only by the Athlete who entered it.
