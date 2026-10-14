---
domain: analytics
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#health_metrics
- kind: code
  role: implementation
  target: frontend/src/components/analytics/HealthMetricsSection.tsx
---

# View health metrics

The Athlete sees the health metrics imported from Apple Health over time, limited to the metrics they track.
