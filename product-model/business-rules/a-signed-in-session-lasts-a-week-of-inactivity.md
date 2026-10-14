---
appliesTo:
- type: capability
  id: sign-in
- type: entity
  id: athlete
references:
- kind: code
  role: implementation
  target: backend/app/api/auth.py#refresh
- kind: code
  role: implementation
  target: backend/app/config.py#Settings
---

# A signed-in session ends after a week without use

Signing in keeps the Athlete signed in on that device; every use renews it, and after seven days without use the Athlete signs in again. An account the operator removed can no longer renew.
