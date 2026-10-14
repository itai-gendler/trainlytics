---
domain: imports
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/imports.py#discard_all
- kind: code
  role: implementation
  target: frontend/src/components/imports/ImportsTab.tsx
---

# Discard all imports

The Athlete dismisses every pending import at once.
