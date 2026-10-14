---
appliesTo:
- type: entity
  id: import
  effect: creates
- type: capability
  id: sync-strava-activities
- type: capability
  id: upload-apple-health-export
references:
- kind: code
  role: implementation
  target: backend/app/services/strava_service.py#_stage_activity
- kind: code
  role: implementation
  target: backend/app/services/apple_health_service.py#_stage_workout
---

# An accepted or discarded import is never staged again

Each Strava activity and each Apple Health workout is staged once; after it is accepted or discarded, later syncs and uploads skip it, while one still pending is refreshed.
