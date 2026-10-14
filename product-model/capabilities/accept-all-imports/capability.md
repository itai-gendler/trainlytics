---
domain: imports
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/imports.py#accept_all
- kind: code
  role: implementation
  target: frontend/src/components/imports/ImportsTab.tsx
---

# Accept all imports

The Athlete turns every pending import into a session at once, oldest first; likely duplicates are left pending.
