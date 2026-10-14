---
domain: plan
references:
- kind: code
  role: implementation
  target: backend/app/models/plan.py#PlannedSession
- kind: code
  role: implementation
  target: backend/app/api/plans.py#_compute_status
---

# Planned session

A strength or cardio session the Athlete planned for a day of a week.

## Information kept

- **Planned date** — the day it is planned for, inside its week
- **Session type** — Strength or Cardio
- **Template** — for strength, the strength template to do
- **Template version** — for strength, the template's version when it was planned
- **Activity type** — for cardio, the activity type to do
- **Title** — the title shown on the plan; a strength session takes the template's name unless given one
- **Notes** — free-text notes
- **Planned segments** — for cardio, the ordered segments, each with an optional title, duration, distance, pace and notes
- **Skip note** — why the session was or will be skipped
- **Order** — its position among the sessions of its day
- **Matched session** — the logged session that completed it

## States

### Planned

Planned for today or a later day, and not done yet.

### Done

A matching session was logged on its planned day.

### Skipped

Its day passed without a matching session, or the Athlete skipped it with a note on Today.
