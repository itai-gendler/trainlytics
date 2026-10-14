---
domain: workout-logging
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: backend/app/api/ai.py#adapt_session
- kind: code
  role: implementation
  target: backend/app/api/ai.py#adapt_cardio_session
- kind: code
  role: implementation
  target: backend/app/services/ai_service.py#call_ai
- kind: code
  role: implementation
  target: frontend/src/components/AdaptSessionModal.tsx
- kind: code
  role: implementation
  target: frontend/src/components/plan/AdaptCardioModal.tsx
- kind: spec
  role: intent
  target: specs/2026-05-16-phase-9-ai-training-coach/requirements.md
  title: 'Phase 9: AI training coach'
---

# Get suggestions to adapt a session

From Adapt this session, the Athlete describes how they feel and asks the AI coach how to change the session they are about to do. The language model is called with the Athlete's own API key; the suggestions change nothing.
