---
domain: analytics
references:
- kind: code
  role: implementation
  target: backend/app/models/body_metrics.py#BodyMetrics
- kind: code
  role: implementation
  target: backend/app/services/apple_health_service.py#_upsert_body_metrics
---

# Health metrics

One day's body and recovery measurements from an Apple Health export.

## Information kept

- **Date** — the day measured
- **Resting heart rate** — resting heart rate in bpm
- **HRV** — heart rate variability (SDNN) in ms
- **Body weight** — body weight in kg
- **Sleep** — time asleep
- **VO2 max** — estimated VO2 max
- **Active energy** — active energy burned in kcal
