---
appliesTo:
- type: entity
  id: strength-session
  effect: changes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#update_session
---

# Only its Athlete changes a strength session

Edits to a strength session are refused for anyone but the Athlete who logged it.
