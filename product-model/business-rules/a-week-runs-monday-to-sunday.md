---
appliesTo:
- type: capability
  id: view-weekly-plan
- type: capability
  id: reschedule-planned-session
- type: entity
  id: weekly-plan
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#_require_monday
- kind: code
  role: implementation
  target: backend/app/models/plan.py#WeeklyPlan
- kind: code
  role: implementation
  target: frontend/src/components/plan/RescheduleModal.tsx
---

# A plan's week runs Monday to Sunday

Every weekly plan starts on a Monday, each Athlete has one plan per week, and a planned session stays inside its week: rescheduling picks a day of the same week and Move to tomorrow is not offered on Sundays.
