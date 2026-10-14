---
actors:
- visitor
access: public
entryPoints:
- web: /login
references:
- kind: code
  role: implementation
  target: frontend/src/pages/LoginPage.tsx
---

# Sign in

Where a Visitor signs in. Every other page sends a Visitor here.
