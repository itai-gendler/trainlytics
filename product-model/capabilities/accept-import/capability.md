---
domain: imports
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/imports.py#accept_import
- kind: code
  role: implementation
  target: backend/app/api/imports.py#_find_duplicate
- kind: code
  role: implementation
  target: frontend/src/components/imports/ImportRow.tsx
---

# Accept an import

The Athlete turns an import into a session.
