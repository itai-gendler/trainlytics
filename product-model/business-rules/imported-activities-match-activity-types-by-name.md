---
appliesTo:
- type: capability
  id: sync-strava-activities
- type: capability
  id: upload-apple-health-export
- type: entity
  id: import
  facts: [Proposed session, Suggested activity type]
references:
- kind: code
  role: implementation
  target: backend/app/services/strava_service.py#map_strava_type
- kind: code
  role: implementation
  target: backend/app/services/apple_health_service.py#map_apple_health_type
---

# Imported activities match activity types by name

An imported cardio activity takes the Athlete's activity type with the same name, ignoring case (Strava's ride kinds count as Cycle); with no match the source's own name is suggested. Strength-like activities become strength sessions without exercises.
