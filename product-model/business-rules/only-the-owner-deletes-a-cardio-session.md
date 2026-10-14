---
appliesTo:
- type: entity
  id: cardio-session
  effect: removes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#delete_session
---

# Only its Athlete deletes a cardio session

A cardio session is deleted only by the Athlete who logged it.
