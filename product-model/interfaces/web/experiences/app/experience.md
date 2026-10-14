---
actors:
- athlete
access: authenticated
entryPoints:
- web: /today
references:
- kind: code
  role: implementation
  target: frontend/src/components/ProtectedRoute.tsx
- kind: code
  role: implementation
  target: frontend/src/components/Layout.tsx
---

# App

The signed-in app. Everything in it is the signed-in Athlete's own training.
