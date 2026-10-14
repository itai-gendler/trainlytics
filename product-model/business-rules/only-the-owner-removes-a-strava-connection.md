---
appliesTo:
- type: entity
  id: strava-connection
  effect: removes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/strava.py#disconnect_strava
---

# Only its Athlete disconnects a Strava connection

Disconnecting Strava removes only the signed-in Athlete's own connection.
