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
  target: frontend/src/lib/strengthSession.ts#parseStrengthDraft
- kind: code
  role: implementation
  target: frontend/src/pages/TodayPage.tsx
- kind: code
  role: implementation
  target: frontend/src/pages/LogWorkoutPage.tsx
---

# Restore a workout draft

The Athlete picks up an unsaved session where they left it: Restore on Log Workout, or Resume on Today.
