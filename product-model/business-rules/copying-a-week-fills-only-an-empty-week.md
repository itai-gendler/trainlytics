---
appliesTo:
- type: capability
  id: copy-plan-from-last-week
- type: entity
  id: weekly-plan
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#copy_from_last_week
---

# Copying last week fills only an empty week

Copy from last week adds last week's sessions seven days later only to a week that has none, without their skip notes and with each template's current version.
