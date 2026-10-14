---
appliesTo:
- type: capability
  id: view-strength-analytics
- type: entity
  id: strength-session
  facts: [Exercises]
references:
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#strength_records
---

# A personal record is an exercise's heaviest set and best single-set volume

For each exercise the records are the heaviest weight lifted, the most reps at that weight, and the highest weight-times-reps of a single set, grouped by exercise type.
