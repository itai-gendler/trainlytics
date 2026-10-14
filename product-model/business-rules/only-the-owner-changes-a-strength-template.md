---
appliesTo:
- type: entity
  id: strength-template
  effect: changes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/templates.py#update_template
---

# Only its Athlete changes a strength template

A template is renamed or given new exercises and sets only by the Athlete who made it.
