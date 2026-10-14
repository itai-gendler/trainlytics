---
domain: settings
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/exercises.py#update_exercise
- kind: code
  role: implementation
  target: frontend/src/pages/SettingsPage.tsx
---

# Edit an exercise

The Athlete changes an exercise's name, notes, exercise types or weight steps.
