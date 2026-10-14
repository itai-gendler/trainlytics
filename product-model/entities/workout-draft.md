---
domain: workout-logging
references:
- kind: code
  role: implementation
  target: frontend/src/lib/draftUtils.ts
- kind: code
  role: implementation
  target: frontend/src/lib/strengthSession.ts#serializeStrengthDraft
- kind: spec
  role: intent
  target: specs/2026-05-10-phase-6-export-draft-recovery/requirements.md
  title: 'Phase 6: export and draft recovery'
---

# Workout draft

A cardio or strength session being logged that is not saved yet, kept on the device so nothing typed is lost.

## Information kept

- **Workout type** — Cardio or Strength; one draft of each at a time
- **Entered values** — everything entered so far, including which sets are done, the current exercise and a running rest timer
- **Started at** — when the workout started
