---
appliesTo:
- type: entity
  id: exercise-type
  effect: changes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/exercise_types.py#update_exercise_type
- kind: code
  role: implementation
  target: backend/app/api/exercises.py#_resolve_types
---

# Only its Athlete changes an exercise type

An exercise type is renamed only by the Athlete who made it, and exercises take only their own Athlete's types.
