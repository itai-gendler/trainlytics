---
domain: connections
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: frontend/src/components/StravaSection.tsx
- kind: code
  role: implementation
  target: backend/app/services/strava_service.py#_after_timestamp
---

# Change the Strava sync start date

The Athlete sets the earliest day whose Strava activities are fetched.
