---
appliesTo:
- type: capability
  id: browse-workout-history
- type: capability
  id: compare-planned-session
- type: capability
  id: view-strength-analytics
- type: entity
  id: strength-session
  facts: [Exercises]
references:
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#list_sessions
- kind: code
  role: implementation
  target: backend/app/api/plan_summary.py#session_comparison
---

# Strength volume is weight times reps

A set's volume is its weight in kg times its reps; sessions, plans, comparisons and charts add up set volumes, and sets missing either count for nothing.
