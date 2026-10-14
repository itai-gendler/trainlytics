---
appliesTo:
- type: entity
  id: exercise
  effect: removes
references:
- kind: code
  role: implementation
  target: backend/app/models/session.py#StrengthExerciseEntry
- kind: code
  role: implementation
  target: backend/app/models/template.py#StrengthTemplateExercise
---

# An exercise listed in a session or template is not deleted

An exercise stays in the library while any strength session or template lists it, so logged history never loses an exercise.
