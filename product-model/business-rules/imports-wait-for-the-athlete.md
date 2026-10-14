---
appliesTo:
- type: entity
  id: import
- type: capability
  id: accept-import
- type: capability
  id: accept-all-imports
references:
- kind: code
  role: implementation
  target: backend/app/api/imports.py#accept_import
- kind: spec
  role: intent
  target: specs/2026-05-23-phase-15-integrations-import-pipeline/requirements.md
  title: 'Phase 15: integrations'
---

# An import becomes a session only when the Athlete accepts it

Fetched Strava activities and Apple Health workouts wait in the import queue; nothing is logged until the Athlete accepts an import, one by one or all at once.
