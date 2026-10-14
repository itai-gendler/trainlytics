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

# Edit the profile

The Athlete keeps the details the AI coach reads: name, birth year, experience level, training goals, injury notes and coach notes. Each field saves as it is changed.
