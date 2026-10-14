---
entities:
- {entity: cardio-session, shows: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Time in heart rate zones, Feeling, Effort, Notes], collects: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Time in heart rate zones, Feeling, Effort, Notes]}
- {entity: strength-session, shows: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes], collects: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}
- {entity: exercise, shows: [Name]}
entryPoints:
- web: /sessions/:id
references:
- kind: code
  role: implementation
  target: frontend/src/pages/CardioSessionDetailPage.tsx
- kind: code
  role: implementation
  target: frontend/src/pages/StrengthSessionDetailPage.tsx
---

# Session

One logged cardio or strength session in full, where it is edited, copied or deleted.
