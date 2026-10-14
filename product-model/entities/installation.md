---
singleton: true
references:
- kind: code
  role: implementation
  target: backend/app/config.py#Settings
- kind: code
  role: implementation
  target: backend/app/services/strava_service.py#is_configured
- kind: doc
  role: context
  target: specs/tech-stack.md
  title: Tech stack
---

# Installation

The one Trainlytics server, as its operator configured it outside the app.

## Information kept

- **Accounts** — the usernames and password hashes of the people who may sign in
- **Strava app** — the Strava API application the operator registered; Strava features exist only while it is set
