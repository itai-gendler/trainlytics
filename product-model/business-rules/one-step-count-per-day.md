---
appliesTo:
- type: capability
  id: log-daily-steps
- type: entity
  id: daily-steps
references:
- kind: code
  role: implementation
  target: backend/app/api/steps.py#upsert_steps
- kind: code
  role: implementation
  target: backend/app/models/step.py#DailySteps
---

# A day has one step count

Entering steps for a day that already has a count replaces it.
