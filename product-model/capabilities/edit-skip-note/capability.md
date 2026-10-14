---
domain: plan
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#update_skip_note
- kind: code
  role: implementation
  target: frontend/src/components/plan/SkipNoteModal.tsx
---

# Edit a skip note

The Athlete adds or changes the reason a skipped session was missed.
