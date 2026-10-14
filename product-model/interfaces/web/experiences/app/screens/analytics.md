---
entities:
- {entity: cardio-session, shows: [Date, Activity type, Segments, Total duration, Time in heart rate zones, Calories, Feeling, Effort]}
- {entity: strength-session, shows: [Date, Exercises, Duration, Calories, Feeling, Effort]}
- {entity: exercise, shows: [Name, Exercise types]}
- {entity: exercise-type, shows: [Name]}
- {entity: activity-type, shows: [Name]}
- {entity: planned-session, shows: [Planned date, Session type]}
- {entity: health-metrics, shows: [Date, Resting heart rate, HRV, Body weight, Sleep, VO2 max, Active energy]}
entryPoints:
- web: /stats
references:
- kind: code
  role: implementation
  target: frontend/src/pages/AnalyticsPage.tsx
---

# Analytics

Stats › Analytics: overview, strength, cardio, readiness, plan adherence and health metrics charts.
