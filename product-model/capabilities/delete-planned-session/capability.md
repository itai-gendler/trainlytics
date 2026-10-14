---
domain: plan
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#delete_planned_session
- kind: code
  role: implementation
  target: frontend/src/components/plan/PlannedSessionCard.tsx
---

# Delete a planned session

The Athlete removes a session from the plan.
