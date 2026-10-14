---
entities:
- {entity: strength-session, shows: [Exercises], collects: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}
- {entity: strength-template, shows: [Exercises]}
- {entity: exercise, shows: [Name, Weight steps]}
- {entity: athlete, shows: [Rest timer length], collects: [Rest timer length]}
- {entity: workout-draft, shows: [Entered values, Started at]}
entryPoints:
- web: /workout
references:
- kind: code
  role: implementation
  target: frontend/src/pages/WorkoutModePage.tsx
---

# Workout mode

A phone-first strength logger, one set at a time, with last time's numbers, a rest timer, the exercise list and Finish.
