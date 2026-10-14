---
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: frontend/src/components/plan/RescheduleModal.tsx
- kind: code
  role: implementation
  target: frontend/src/pages/TodayPage.tsx
- kind: code
  role: implementation
  target: backend/app/api/plans.py#update_planned_session
---

# Reschedule a planned session

The Athlete moves a planned session to another day of its week, from Plan or, for tomorrow, from Today.
