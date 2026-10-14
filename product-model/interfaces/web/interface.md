---
type: web
actors:
- visitor
- athlete
languages:
- en
entryPoints:
- web: /login
- web: /today
references:
- kind: code
  role: implementation
  target: frontend/src/App.tsx
- kind: code
  role: implementation
  target: frontend/src/components/Layout.tsx
- kind: code
  role: implementation
  target: backend/app/main.py
---

# Web app

The Trainlytics web app, usable on desktop and installable on a phone: the sign-in page, and the
signed-in app with Today, Plan, Stats, Log Workout, Templates, Steps, Profile and Settings.
