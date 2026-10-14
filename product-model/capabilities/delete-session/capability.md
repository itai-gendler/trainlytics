---
domain: history
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#delete_session
- kind: code
  role: implementation
  target: frontend/src/pages/CardioSessionDetailPage.tsx
- kind: code
  role: implementation
  target: frontend/src/pages/StrengthSessionDetailPage.tsx
---

# Delete a session

The Athlete deletes a logged session.
