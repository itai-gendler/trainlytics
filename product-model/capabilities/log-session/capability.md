---
domain: workout-logging
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#create_cardio_session
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#create_strength_session
- kind: code
  role: implementation
  target: frontend/src/pages/LogWorkoutPage.tsx
- kind: code
  role: implementation
  target: frontend/src/pages/WorkoutModePage.tsx
- kind: code
  role: implementation
  target: frontend/src/lib/hooks/useStrengthSessionForm.ts#useStrengthSessionForm
- kind: code
  role: implementation
  target: frontend/src/lib/strengthSession.ts#computeDiff
- kind: code
  role: implementation
  target: frontend/src/lib/planStart.ts#getStartUrl
- kind: spec
  role: intent
  target: specs/2026-05-04-phase-2-strength-templates/requirements.md
  title: 'Phase 2: strength templates'
- kind: spec
  role: intent
  target: specs/2026-10-05-phase-17-mobile-redesign/requirements.md
  title: 'Phase 17: mobile redesign'
---

# Log a session

The Athlete records a cardio or strength session: from Log Workout, from a planned session's Start, from a template's Use, or set by set in workout mode on a phone. What is typed is kept as a draft until the session is saved, and a matching planned session of that day becomes Done.
