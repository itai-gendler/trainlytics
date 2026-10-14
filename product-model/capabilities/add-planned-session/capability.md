---
domain: plan
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#add_planned_session
- kind: code
  role: implementation
  target: backend/app/schemas/plan.py#PlannedSessionIn
- kind: code
  role: implementation
  target: frontend/src/components/plan/PlanSessionForm.tsx
---

# Add a planned session

The Athlete adds a strength session from a template, or a cardio session of an activity type with its segments, to a day of the week.
