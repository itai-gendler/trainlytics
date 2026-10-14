---
domain: history
references:
- kind: code
  role: implementation
  target: backend/app/models/session.py#CardioSession
- kind: code
  role: implementation
  target: backend/app/schemas/session.py#CardioSessionCreate
---

# Cardio session

A logged cardio workout, such as a run, ride or walk, made of one or more segments.

## Information kept

- **Date** — the date and time it took place
- **Title** — an optional title; the form suggests one such as "Run – 8 km"
- **Activity type** — the Athlete's activity type the session is
- **Segments** — the ordered parts of the session, each with a duration, an optional distance, pace and title
- **Total duration** — an optional total that overrides the sum of the segments' durations
- **Calories** — optional calories burned
- **Average heart rate** — optional average heart rate in bpm
- **Time in heart rate zones** — optional seconds spent in each of the five heart rate zones
- **Feeling** — how the Athlete felt beforehand, 1 to 5 from Exhausted to Great
- **Effort** — how hard the session was, 1 to 10 where 10 is maximal effort
- **Notes** — free-text notes
