---
domain: templates
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/templates.py#update_template
- kind: code
  role: implementation
  target: frontend/src/pages/TemplatesPage.tsx
---

# Edit a strength template

The Athlete renames a template or changes its exercises and sets; every change to the exercises or sets is a new version.
