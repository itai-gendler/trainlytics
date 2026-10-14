---
appliesTo:
- type: capability
  id: sign-in
- type: entity
  id: installation
references:
- kind: code
  role: implementation
  target: backend/app/auth.py#parse_users
- kind: code
  role: implementation
  target: backend/app/auth.py#authenticate_user
- kind: doc
  role: intent
  target: README.md
  title: 'README: Deployment'
---

# Only accounts the operator configured can sign in

The server's operator lists each username with a password hash in the server configuration; there is no registration, and the app cannot change or reset a password.
