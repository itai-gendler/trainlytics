---
appliesTo:
- type: entity
  id: strava-connection
  effect: changes
permits:
- related:
  - {verb: owns, entity: athlete}
references:
- kind: code
  role: implementation
  target: backend/app/api/strava.py#fetch_activities
- kind: code
  role: implementation
  target: backend/app/api/profile.py#patch_profile
---

# Only its Athlete changes a Strava connection

A Strava connection's sync start date and syncs belong to the Athlete who connected it.
