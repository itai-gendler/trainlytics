---
appliesTo:
- type: capability
  id: add-planned-session
- type: capability
  id: edit-planned-session
- type: entity
  id: planned-session
references:
- kind: code
  role: implementation
  target: backend/app/schemas/plan.py#PlannedSessionIn
---

# A planned session says what to do

A planned strength session names one of the Athlete's templates; a planned cardio session names an activity type and has at least one segment.
