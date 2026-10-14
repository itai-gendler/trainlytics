---
appliesTo:
- type: entity
  id: exercise-type
  effect: removes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/exercise_types.py#delete_exercise_type
---

# Only its Athlete deletes an exercise type

An exercise type is deleted only by the Athlete who made it.
