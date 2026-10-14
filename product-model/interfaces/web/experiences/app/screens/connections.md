---
entities:
- {entity: strava-connection, shows: [Strava athlete name, Strava athlete photo, Sync start date, Last synced], collects: [Sync start date]}
- {entity: athlete, shows: [Tracked health metrics], collects: [Tracked health metrics]}
entryPoints:
- web: /profile?tab=connections
references:
- kind: code
  role: implementation
  target: frontend/src/pages/ProfilePage.tsx
- kind: code
  role: implementation
  target: frontend/src/components/StravaSection.tsx
- kind: code
  role: implementation
  target: frontend/src/components/AppleHealthSection.tsx
---

# Connections

Profile › Connections: Strava and Apple Health, with the tracked health metrics.
