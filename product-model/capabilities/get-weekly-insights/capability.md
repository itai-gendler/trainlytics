---
domain: history
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/ai.py#weekly_insights
- kind: code
  role: implementation
  target: backend/app/services/ai_service.py#call_weekly_insights
- kind: code
  role: implementation
  target: frontend/src/components/WeeklyInsightsCard.tsx
---

# Get weekly insights

The Athlete asks the AI coach to analyse the current week against the previous five. The language model is called with the Athlete's own API key.
