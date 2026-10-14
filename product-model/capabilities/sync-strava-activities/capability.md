---
domain: connections
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/strava.py#fetch_activities
- kind: code
  role: implementation
  target: backend/app/services/strava_service.py#fetch_activities_worker
- kind: code
  role: implementation
  target: backend/app/services/strava_service.py#map_strava_type
- kind: code
  role: implementation
  target: frontend/src/components/StravaSection.tsx
---

# Sync Strava activities

The Athlete fetches their Strava activities into the import queue. Offered while Strava is connected.
