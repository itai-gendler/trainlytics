---
appliesTo:
- type: entity
  id: strength-session
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
  target: backend/app/api/exercises.py#get_last_session_defaults
---

# Only its Athlete sees a strength session

A strength session is listed, opened, charted, used for last-session defaults and given to the AI coach only for the Athlete who logged it.
