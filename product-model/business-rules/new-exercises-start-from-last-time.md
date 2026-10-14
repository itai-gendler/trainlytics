---
appliesTo:
- type: capability
  id: log-session
- type: entity
  id: strength-session
references:
- kind: code
  role: implementation
  target: backend/app/api/exercises.py#get_last_session_defaults
- kind: code
  role: implementation
  target: frontend/src/lib/strengthSession.ts#fetchLastSessionSets
- kind: spec
  role: intent
  target: specs/2026-10-07-per-set-rpe/requirements.md
  title: Per-set RPE
---

# An exercise added to a session starts with its last sets

An exercise added while logging starts with the reps and weight of the sets in the latest session that had it; set effort is never prefilled, from that session or from a template.
