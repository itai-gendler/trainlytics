---
appliesTo:
- type: entity
  id: activity-type
  effect: changes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/cardio_types.py#update_cardio_type
---

# Only its Athlete changes an activity type

An activity type is renamed only by the Athlete who made it.
