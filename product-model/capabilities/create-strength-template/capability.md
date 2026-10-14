---
domain: templates
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/templates.py#create_template
- kind: code
  role: implementation
  target: frontend/src/pages/TemplatesPage.tsx
---

# Create a strength template

The Athlete saves a reusable strength workout: a name and exercises with their sets of reps and weight.
