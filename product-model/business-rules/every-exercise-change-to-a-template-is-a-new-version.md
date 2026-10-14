---
appliesTo:
- type: entity
  id: strength-template
  facts: [Version, Version history]
- type: capability
  id: compare-planned-session
references:
- kind: code
  role: implementation
  target: backend/app/services/template_versioning.py#_write_template_history
- kind: code
  role: implementation
  target: backend/app/api/plan_summary.py#session_comparison
- kind: spec
  role: intent
  target: specs/2026-05-17-phase-14-plan-vs-actual-deep-analytics/requirements.md
  title: 'Phase 14: plan vs actual'
---

# Every change to a template's exercises is a new version

Creating a template saves version 1, and each change to its exercises or sets saves the next version; renaming keeps the version. A planned strength session keeps the version it was planned with, and its comparison uses that version.

## Rationale

A template keeps evolving while old plans should still be compared with what was planned at the time.
