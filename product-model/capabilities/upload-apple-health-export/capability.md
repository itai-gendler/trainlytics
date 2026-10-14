---
domain: connections
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/apple_health.py#upload_apple_health
- kind: code
  role: implementation
  target: backend/app/services/apple_health_service.py#parse_xml_worker
- kind: code
  role: implementation
  target: frontend/src/components/AppleHealthSection.tsx
- kind: spec
  role: intent
  target: specs/2026-05-23-phase-15-integrations-import-pipeline/requirements.md
  title: 'Phase 15: integrations'
---

# Upload an Apple Health export

The Athlete uploads the export zip from their iPhone; its workouts go to the import queue and its daily health metrics are saved.
