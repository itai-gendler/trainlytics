---
domain: analytics
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#plan_adherence
- kind: code
  role: implementation
  target: frontend/src/components/analytics/PlanAdherenceChart.tsx
---

# View plan adherence

The Athlete sees, for each of the last completed weeks, how many planned sessions were done or skipped and how planned volume and distance compare with what was done.
