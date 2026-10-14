---
appliesTo:
- type: capability
  id: view-plan-adherence
- type: entity
  id: planned-session
references:
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#plan_adherence
---

# Plan adherence covers completed weeks only

Plan adherence charts the past twelve weeks that have ended; the current week is left out until it is over.
