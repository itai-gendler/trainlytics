---
domain: history
references:
- kind: code
  role: implementation
  target: backend/app/models/session.py#StrengthSession
- kind: code
  role: implementation
  target: backend/app/schemas/session.py#StrengthSessionCreate
---

# Strength session

A logged strength workout: the exercises done, in order, with their sets.

## Information kept

- **Date** — the date and time it took place
- **Title** — an optional title; the template's name or "Strength session" by default
- **Template** — the strength template it was started from, if any
- **Exercises** — the ordered exercises, each with numbered sets of reps, weight in kg, an optional set effort from 1 to 10 and an optional set note
- **Duration** — how long the session took
- **Calories** — optional calories burned
- **Feeling** — how the Athlete felt beforehand, 1 to 5 from Exhausted to Great
- **Effort** — how hard the session was, 1 to 10 where 10 is maximal effort
- **Notes** — free-text notes
