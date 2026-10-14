---
entities:
- {entity: planned-session, shows: [Planned date, Session type, Title, Planned segments, Skip note, Matched session], collects: [Skip note]}
- {entity: workout-draft, shows: [Workout type, Started at]}
entryPoints:
- web: /today
references:
- kind: code
  role: implementation
  target: frontend/src/pages/TodayPage.tsx
---

# Today

Today's date, a card for each session planned today with Start, Move to tomorrow and Skip, a Resume card per unsaved draft, Quick log, and this week's progress.
