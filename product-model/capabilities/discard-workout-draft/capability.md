---
domain: workout-logging
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: frontend/src/lib/draftUtils.ts
- kind: code
  role: implementation
  target: frontend/src/pages/LogWorkoutPage.tsx
---

# Discard a workout draft

The Athlete throws away an unsaved session to start fresh.
