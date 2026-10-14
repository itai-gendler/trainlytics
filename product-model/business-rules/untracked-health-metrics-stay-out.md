---
appliesTo:
- type: entity
  id: health-metrics
- type: entity
  id: athlete
  facts: [Tracked health metrics]
- type: capability
  id: view-health-metrics
references:
- kind: code
  role: implementation
  target: backend/app/services/apple_health_service.py#_process_record
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#health_metrics
- kind: code
  role: implementation
  target: backend/app/services/ai_service.py#get_health_context_block
---

# An untracked health metric is not imported, shown or given to the AI coach

Only the health metrics the Athlete tracks are read from an Apple Health export, charted in Analytics and included in AI requests.
