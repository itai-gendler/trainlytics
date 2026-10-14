---
appliesTo:
- type: entity
  id: strength-session
  effect: removes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#delete_session
---

# Only its Athlete deletes a strength session

A strength session is deleted only by the Athlete who logged it.
