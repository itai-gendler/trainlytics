---
appliesTo:
- type: capability
  id: accept-import
- type: capability
  id: accept-all-imports
- type: entity
  id: import
references:
- kind: code
  role: implementation
  target: backend/app/api/imports.py#_find_duplicate
---

# A likely duplicate import is held for the Athlete

An import is a likely duplicate when a session the Athlete logged within a day of it lasted within a minute of it. Accepting it one by one shows the existing session first; Accept all leaves it pending.
