---
domain: steps
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/steps.py#upsert_steps
- kind: code
  role: implementation
  target: frontend/src/components/StepsForm.tsx
---

# Log daily steps

The Athlete records how many steps they walked on a day; a day has one count.
