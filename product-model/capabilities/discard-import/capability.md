---
domain: imports
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/imports.py#discard_import
- kind: code
  role: implementation
  target: frontend/src/components/imports/ImportRow.tsx
---

# Discard an import

The Athlete dismisses an import without logging it.
