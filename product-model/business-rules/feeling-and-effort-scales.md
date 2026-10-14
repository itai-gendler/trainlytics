---
appliesTo:
- type: entity
  id: cardio-session
  facts: [Feeling, Effort]
- type: entity
  id: strength-session
  facts: [Feeling, Effort, Exercises]
references:
- kind: code
  role: implementation
  target: backend/app/schemas/session.py#StrengthSetCreate
- kind: code
  role: implementation
  target: frontend/src/components/emojiRatingOptions.ts
- kind: spec
  role: intent
  target: specs/2026-10-07-rpe/requirements.md
  title: Session RPE on 1–10
---

# Feeling is rated 1 to 5 and effort 1 to 10

Feeling before a session runs from 1 (Exhausted) to 5 (Great); session effort and set effort run from 1 to 10, where 10 is maximal effort. Values outside these ranges are refused.
