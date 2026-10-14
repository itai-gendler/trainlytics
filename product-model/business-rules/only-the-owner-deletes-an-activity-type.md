---
appliesTo:
- type: entity
  id: activity-type
  effect: removes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/cardio_types.py#delete_cardio_type
---

# Only its Athlete deletes an activity type

An activity type is deleted only by the Athlete who made it.
