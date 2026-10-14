---
appliesTo:
- type: entity
  id: exercise
  effect: changes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/exercises.py#update_exercise
- kind: code
  role: implementation
  target: backend/app/api/exercises.py#add_replacement
---

# Only its Athlete changes an exercise

An exercise, its weight steps and its replacements are changed only by the Athlete whose library holds it; a replacement must be one of their own exercises too.
