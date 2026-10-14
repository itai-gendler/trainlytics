---
appliesTo:
- type: capability
  id: sync-strava-activities
- type: entity
  id: strava-connection
  facts: [Sync start date, Last synced]
references:
- kind: code
  role: implementation
  target: backend/app/services/strava_service.py#_after_timestamp
- kind: code
  role: implementation
  target: backend/app/api/strava.py#disconnect_strava
---

# Strava sync fetches from the later of the start date and the last sync

Sync now fetches activities that started after the sync start date or the last sync, whichever is later; disconnecting forgets both.
