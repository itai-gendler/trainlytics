---
entities:
- {entity: weekly-plan, shows: [Week start]}
- {entity: planned-session, shows: [Planned date, Session type, Template, Activity type, Title, Notes, Planned segments, Skip note, Order, Matched session], collects: [Planned date, Session type, Template, Activity type, Title, Notes, Planned segments, Skip note]}
- {entity: strength-template, shows: [Name, Exercises, Version history]}
- {entity: activity-type, shows: [Name]}
- {entity: cardio-session, shows: [Segments, Total duration]}
- {entity: strength-session, shows: [Exercises]}
entryPoints:
- web: /plan
references:
- kind: code
  role: implementation
  target: frontend/src/pages/PlanPage.tsx
---

# Plan

One Monday-to-Sunday week: its planned sessions day by day with their status, the week's counts, planned against actual totals, and each done session's comparison.
