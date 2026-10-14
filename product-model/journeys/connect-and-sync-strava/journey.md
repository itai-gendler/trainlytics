---
actors:
- athlete
references:
- kind: code
  role: implementation
  target: backend/app/api/strava.py#strava_callback
- kind: code
  role: implementation
  target: frontend/src/components/StravaSection.tsx
---

# Connect and sync Strava

## Goal

The Athlete brings their Strava activities into Trainlytics.

## Success criterion

Strava is connected and its activities wait in Imports.
