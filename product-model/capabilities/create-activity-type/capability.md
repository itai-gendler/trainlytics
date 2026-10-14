---
domain: settings
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/cardio_types.py#create_cardio_type
- kind: code
  role: implementation
  target: frontend/src/pages/SettingsPage.tsx
---

# Create an activity type

The Athlete adds a kind of cardio, such as Run or Cycle, to log and plan.
