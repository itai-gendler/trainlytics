---
domain: today
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#_compute_status
- kind: code
  role: implementation
  target: backend/app/api/plans.py#update_skip_note
- kind: code
  role: implementation
  target: frontend/src/components/plan/SkipNoteModal.tsx
- kind: code
  role: implementation
  target: frontend/src/pages/TodayPage.tsx
---

# Skip a planned session

A planned session becomes Skipped: the Athlete skips one of today's sessions with a reason, or its day passes without a matching session being logged.
