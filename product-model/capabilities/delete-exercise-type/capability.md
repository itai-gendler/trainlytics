---
domain: settings
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/exercise_types.py#delete_exercise_type
---

# Delete an exercise type

The Athlete deletes an exercise type; the exercises tagged with it lose the tag.
