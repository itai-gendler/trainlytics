---
appliesTo:
- type: entity
  id: strength-template
  effect: reads
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/templates.py#_load_template
- kind: code
  role: implementation
  target: backend/app/api/plans.py#add_planned_session
---

# Only its Athlete sees a strength template

Templates are listed, opened, used and planned only by the Athlete who made them.
