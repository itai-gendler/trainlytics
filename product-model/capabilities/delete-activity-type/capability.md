---
domain: settings
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/cardio_types.py#delete_cardio_type
- kind: code
  role: implementation
  target: backend/app/models/session.py#CardioSession
---

# Delete an activity type

The Athlete deletes an activity type; sessions and planned sessions of that type stay, without a type.
