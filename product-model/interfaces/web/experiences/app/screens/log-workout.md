---
entities:
- {entity: cardio-session, collects: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Time in heart rate zones, Feeling, Effort, Notes]}
- {entity: strength-session, shows: [Exercises], collects: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}
- {entity: strength-template, shows: [Name, Exercises]}
- {entity: exercise, shows: [Name, Notes, Replacements], collects: [Name]}
- {entity: activity-type, shows: [Name]}
- {entity: planned-session, shows: [Title, Activity type, Planned segments, Planned date]}
- {entity: workout-draft, shows: [Workout type, Entered values, Started at]}
entryPoints:
- web: /log
references:
- kind: code
  role: implementation
  target: frontend/src/pages/LogWorkoutPage.tsx
---

# Log Workout

The full form for logging a cardio or a strength session, with template choice, drafts, the template-change prompt and Adapt this session.
