---
domain: analytics
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#get_summary
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#heatmap
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#overview_trends
- kind: code
  role: implementation
  target: frontend/src/components/analytics/StatsGlance.tsx
- kind: code
  role: implementation
  target: frontend/src/components/analytics/ConsistencyHeatmap.tsx
---

# View the training overview

The Athlete sees their training at a glance: this week's sessions against the plan, all-time totals, a year of consistency and weekly training time.
