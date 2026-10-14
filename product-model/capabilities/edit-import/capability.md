---
domain: imports
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/imports.py#patch_import
- kind: code
  role: implementation
  target: frontend/src/components/imports/ImportRow.tsx
---

# Edit an import

Before accepting, the Athlete corrects an import's date, activity type, title or notes.
