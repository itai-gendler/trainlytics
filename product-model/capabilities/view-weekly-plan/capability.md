---
domain: plan
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#get_week_plan
- kind: code
  role: implementation
  target: backend/app/api/plan_summary.py#plan_weekly_summary
- kind: code
  role: implementation
  target: frontend/src/pages/PlanPage.tsx
- kind: code
  role: implementation
  target: frontend/src/components/plan/WeekGrid.tsx
- kind: code
  role: implementation
  target: frontend/src/components/plan/WeeklyOverviewCard.tsx
- kind: code
  role: implementation
  target: frontend/src/components/plan/PlanVsActualCard.tsx
---

# View the weekly plan

The Athlete sees a week's plan day by day with each session's status, the week's counts and completion, and planned against actual totals.
