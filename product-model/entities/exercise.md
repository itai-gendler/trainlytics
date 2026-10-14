---
domain: settings
references:
- kind: code
  role: implementation
  target: backend/app/models/exercise.py#Exercise
- kind: code
  role: implementation
  target: backend/app/schemas/exercise.py#ExerciseCreate
---

# Exercise

An exercise in the Athlete's library, such as Back Squat, that strength sessions and templates list.

## Information kept

- **Name** — the exercise's name
- **Notes** — cues shown as a hint when the exercise is logged
- **Exercise types** — the exercise types it is tagged with, which group it in pickers and analytics
- **Weight steps** — how workout mode's weight buttons step: the default 10 lb machine stack, a stack of given plates, or a fixed kg step
- **Replacements** — other exercises of the Athlete's that can stand in for it
