---
domain: templates
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/templates.py#delete_template
- kind: code
  role: implementation
  target: backend/app/models/plan.py#PlannedSession
---

# Delete a strength template

The Athlete deletes a template. Sessions logged from it keep their exercises, and planned sessions keep their day and title but no longer name it.
