---
domain: analytics
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#strength_records
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#strength_volume_by_tag
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#strength_exercises_by_type
- kind: code
  role: implementation
  target: frontend/src/components/analytics/PersonalRecordsPanel.tsx
---

# View strength analytics

The Athlete sees strength volume by exercise type, exercises per type each week, an exercise's progression and personal records.
