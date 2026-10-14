---
domain: profile
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/profile.py#patch_profile
- kind: code
  role: implementation
  target: frontend/src/pages/ProfilePage.tsx
---

# Remove the AI key

The Athlete removes their saved API key, which turns AI coaching off.
