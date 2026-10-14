---
domain: connections
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: frontend/src/components/AppleHealthSection.tsx
- kind: code
  role: implementation
  target: backend/app/api/profile.py#patch_profile
---

# Change tracked health metrics

The Athlete turns each health metric on or off; an untracked metric is not imported, charted or given to the AI coach.
