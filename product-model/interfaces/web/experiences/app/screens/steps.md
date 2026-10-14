---
entities:
- {entity: daily-steps, shows: [Date, Steps], collects: [Date, Steps]}
entryPoints:
- web: /steps
references:
- kind: code
  role: implementation
  target: frontend/src/pages/StepsPage.tsx
---

# Steps

Daily step counts, newest first, with a form to add one.
