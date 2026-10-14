---
appliesTo:
- type: entity
  id: cardio-session
  effect: changes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#update_session
---

# Only its Athlete changes a cardio session

Edits to a cardio session are refused for anyone but the Athlete who logged it.
