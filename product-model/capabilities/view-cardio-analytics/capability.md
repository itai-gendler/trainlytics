---
domain: analytics
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#hr_zone_trends
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#cardio_time_split
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#cardio_distance_progression
- kind: code
  role: implementation
  target: backend/app/api/analytics.py#training_load
- kind: code
  role: implementation
  target: backend/app/services/sessions.py#get_pace_trends
---

# View cardio analytics

The Athlete sees heart rate zone trends, how cardio time splits across activity types, walking segments, distance progression, pace trends and training load.
