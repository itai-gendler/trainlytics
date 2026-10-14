---
domain: today
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: frontend/src/pages/TodayPage.tsx
- kind: code
  role: implementation
  target: frontend/src/lib/planApi.ts#useUpdateSkipNote
---

# Undo skip

The Athlete takes back a skip made on Today, so the session is planned again.
