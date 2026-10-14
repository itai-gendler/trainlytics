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
  target: backend/app/services/crypto.py
- kind: code
  role: implementation
  target: frontend/src/pages/ProfilePage.tsx
---

# Save an AI key

The Athlete chooses Anthropic or OpenAI and saves their own API key, which turns on AI coaching.
