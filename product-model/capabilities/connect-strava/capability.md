---
domain: connections
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/strava.py#get_auth_url
- kind: code
  role: implementation
  target: backend/app/api/strava.py#strava_callback
- kind: code
  role: implementation
  target: frontend/src/components/StravaSection.tsx
---

# Connect Strava

The Athlete links their Strava account so its activities can be fetched. Offered only while the server's operator has set up a Strava app.
