---
appliesTo:
- type: capability
  id: view-weekly-plan
- type: capability
  id: view-today
- type: entity
  id: planned-session
references:
- kind: code
  role: implementation
  target: frontend/src/lib/planStats.ts
---

# Completion is done sessions out of done and skipped ones

A week's completion is its Done sessions divided by its Done and Skipped ones; sessions still Planned do not count.
