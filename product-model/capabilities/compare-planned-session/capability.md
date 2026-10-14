---
domain: plan
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/plan_summary.py#session_comparison
- kind: code
  role: implementation
  target: frontend/src/components/plan/SessionComparisonPanel.tsx
---

# Compare a planned session with what was done

On a done session the Athlete opens Compare planned vs. actual, a side-by-side of plan and actual: exercises, sets and volume for strength, distance and time for cardio, with the difference in percent.
