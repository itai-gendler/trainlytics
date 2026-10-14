---
availability:
- {place: 'web::sign-in'}
references:
- kind: code
  role: implementation
  target: backend/app/api/auth.py#login
- kind: code
  role: implementation
  target: backend/app/api/auth.py#refresh
- kind: code
  role: implementation
  target: backend/app/auth.py#authenticate_user
- kind: code
  role: implementation
  target: frontend/src/pages/LoginPage.tsx
- kind: code
  role: implementation
  target: frontend/src/contexts/AuthContext.tsx
---

# Sign in

A Visitor signs in with the username and password the server's operator set up for them. A signed-in session stays open while the app is used at least once a week.
