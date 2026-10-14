---
appliesTo:
- type: capability
  id: add-exercise-replacement
- type: entity
  id: exercise
  facts: [Replacements]
references:
- kind: code
  role: implementation
  target: backend/app/api/exercises.py#add_replacement
---

# An exercise is never its own replacement

A replacement is another of the Athlete's exercises, listed once.
