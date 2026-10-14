---
domain: imports
references:
- kind: code
  role: implementation
  target: backend/app/models/pending_import.py#PendingImport
- kind: code
  role: implementation
  target: backend/app/api/imports.py#_create_session_from_import
---

# Import

An activity brought in from Strava or an Apple Health export, waiting to become a session.

## Information kept

- **Source** — Strava or Apple Health
- **Proposed session** — the session it would become: strength or cardio, date, activity type, title, notes, duration, distance, calories, average heart rate and segments
- **Suggested activity type** — the source's own activity name when none of the Athlete's activity types matched it

## States

### Pending

Waiting in the import queue for the Athlete.

### Accepted

Turned into a session.

### Discarded

Dismissed without creating a session.
