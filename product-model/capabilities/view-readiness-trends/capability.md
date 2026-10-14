---
domain: analytics
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#readiness_trends
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#readiness_correlation
---

# View readiness trends

The Athlete sees how feeling before training and effort have moved week by week, and how they relate.
