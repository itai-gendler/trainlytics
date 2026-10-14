---
domain: connections
references:
- kind: code
  role: implementation
  target: backend/app/api/strava.py#strava_callback
- kind: code
  role: implementation
  target: backend/app/models/user_settings.py#UserSettings
---

# Strava connection

The link between the Athlete and their Strava account, through which their activities are fetched.

## Information kept

- **Strava athlete name** — the name of the connected Strava account
- **Strava athlete photo** — its profile photo
- **Sync start date** — the earliest day whose activities are fetched
- **Last synced** — when activities were last fetched
