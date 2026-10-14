---
appliesTo:
- type: entity
  id: exercise
  effect: removes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/exercises.py#delete_exercise
---

# Only its Athlete deletes an exercise

An exercise is deleted only by the Athlete whose library holds it.
