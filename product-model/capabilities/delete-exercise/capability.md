---
domain: settings
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/exercises.py#delete_exercise
- kind: code
  role: implementation
  target: backend/app/models/session.py#StrengthExerciseEntry
---

# Delete an exercise

The Athlete deletes an exercise that no session or template uses.
