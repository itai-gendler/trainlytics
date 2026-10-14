---
appliesTo:
- type: capability
  id: get-weekly-insights
- type: capability
  id: get-session-suggestions
- type: entity
  id: planned-session
references:
- kind: code
  role: implementation
  target: backend/app/api/ai.py#adapt_session
---

# AI coaching never changes the Athlete's training

Weekly insights and session suggestions are text for the Athlete to read; they never change a plan, template or session.
