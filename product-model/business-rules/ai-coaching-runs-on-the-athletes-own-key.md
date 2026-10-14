---
appliesTo:
- type: capability
  id: get-weekly-insights
- type: capability
  id: get-session-suggestions
- type: entity
  id: athlete
  facts: [AI provider, AI key]
references:
- kind: code
  role: implementation
  target: backend/app/services/ai_service.py#get_active_provider
- kind: code
  role: implementation
  target: backend/app/api/ai.py#weekly_insights
---

# AI coaching runs on the Athlete's own API key

Weekly insights and session suggestions call the language model of the Athlete's chosen provider with the Athlete's own key; without a saved key they make no request and say to add one in the profile.
