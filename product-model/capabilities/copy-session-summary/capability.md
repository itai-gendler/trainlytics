---
domain: history
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: frontend/src/lib/exportUtils.ts#formatStrengthSession
- kind: code
  role: implementation
  target: frontend/src/lib/exportUtils.ts#formatCardioSession
- kind: spec
  role: intent
  target: specs/2026-05-10-phase-6-export-draft-recovery/requirements.md
  title: 'Phase 6: export and draft recovery'
---

# Copy a session summary

The Athlete copies a session as structured text, ready to paste into an AI tool or send to a coach.
