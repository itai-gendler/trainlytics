---
appliesTo:
- type: entity
  id: strava-connection
  effect: creates
permits:
- actors:
  - athlete
  when:
  - {entity: installation, fact: Strava app, present: true}
references:
- kind: code
  role: implementation
  target: backend/app/api/strava.py#_require_strava
- kind: code
  role: implementation
  target: backend/app/services/strava_service.py#is_configured
---

# Strava connects only when the server has a Strava app

Connect Strava, syncing and the Strava section exist only while the operator has registered a Strava app on the server; without it Strava requests are refused as not configured.
