---
domain: settings
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/exercises.py#add_replacement
- kind: code
  role: implementation
  target: frontend/src/pages/SettingsPage.tsx
---

# Add an exercise replacement

The Athlete names another of their exercises as a stand-in for an exercise, to swap in while logging and for the AI coach to suggest.
