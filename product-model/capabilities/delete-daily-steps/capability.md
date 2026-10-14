---
domain: steps
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/steps.py#delete_steps
- kind: code
  role: implementation
  target: frontend/src/pages/StepsPage.tsx
---

# Delete daily steps

The Athlete deletes a day's step count.
