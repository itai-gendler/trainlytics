---
appliesTo:
- type: capability
  id: get-weekly-insights
- type: capability
  id: get-session-suggestions
- type: entity
  id: athlete
  facts: [Experience level, Birth year, Training goals, Injury notes, Coach notes]
references:
- kind: code
  role: implementation
  target: backend/app/services/ai_service.py#build_athlete_context_block
- kind: code
  role: implementation
  target: backend/app/services/ai_service.py#get_health_context_block
---

# Every AI request carries the athlete's profile and recent health

Each AI request starts with the Athlete's experience, age, goals by priority, injury notes and coach notes, followed by seven-day averages of their tracked health metrics now and a month, three months and a year ago.
