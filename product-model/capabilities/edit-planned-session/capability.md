---
domain: plan
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#update_planned_session
- kind: code
  role: implementation
  target: frontend/src/components/plan/PlannedSessionCard.tsx
- kind: code
  role: implementation
  target: frontend/src/components/plan/PlanSessionForm.tsx
---

# Edit a planned session

The Athlete changes what a planned or skipped session is: its type, template or activity type, title, notes and segments. On a skipped session the control reads Swap.
