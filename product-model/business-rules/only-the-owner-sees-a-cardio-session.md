---
appliesTo:
- type: entity
  id: cardio-session
  effect: reads
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#get_session
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#list_sessions
---

# Only its Athlete sees a cardio session

A cardio session is listed, opened, charted and given to the AI coach only for the Athlete who logged it.
