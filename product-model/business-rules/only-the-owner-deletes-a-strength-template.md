---
appliesTo:
- type: entity
  id: strength-template
  effect: removes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/templates.py#delete_template
---

# Only its Athlete deletes a strength template

A template is deleted only by the Athlete who made it.
