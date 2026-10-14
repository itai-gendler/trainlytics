---
appliesTo:
- type: entity
  id: planned-session
  effect: changes
  to: Done
references:
- kind: code
  role: implementation
  target: backend/app/api/plans.py#_compute_status
- kind: spec
  role: intent
  target: specs/2026-05-16-phase-11-planning-weekly-overview/requirements.md
  title: 'Phase 11: planning'
---

# A planned session is done when a matching session is logged on its day

A planned strength session is Done when a strength session from the same template, or from no template, is logged on its planned day; a planned cardio session is Done when a cardio session of the same activity type is logged that day. Deleting or moving that session undoes it.

## Rationale

The status is worked out from what was logged, so the plan stays true however the session was logged: from the plan, from Today, from a template or by hand.
