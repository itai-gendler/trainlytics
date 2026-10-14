---
domain: plan
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#copy_from_last_week
- kind: code
  role: implementation
  target: frontend/src/pages/PlanPage.tsx
---

# Copy the plan from last week

The Athlete fills an empty week with the previous week's sessions, each moved seven days later.
