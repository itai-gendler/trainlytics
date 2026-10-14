---
domain: settings
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/exercises.py#create_exercise
- kind: code
  role: implementation
  target: backend/app/schemas/exercise.py#StackWeightScale
- kind: code
  role: implementation
  target: frontend/src/pages/SettingsPage.tsx
- kind: code
  role: implementation
  target: frontend/src/components/ExerciseEntryBlock.tsx
---

# Create an exercise

The Athlete adds an exercise to their library, in Settings › Exercises or straight from the strength log form.
