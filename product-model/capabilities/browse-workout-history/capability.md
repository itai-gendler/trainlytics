---
domain: history
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#list_sessions
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#weekly_summary
- kind: code
  role: implementation
  target: backend/app/api/sessions.py#training_trends
- kind: code
  role: implementation
  target: frontend/src/pages/HistoryPage.tsx#HistoryPageContent
---

# Browse the workout history

The Athlete looks through every logged session, newest first, with this week's totals and the trends of recent weeks.
