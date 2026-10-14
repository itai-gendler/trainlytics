---
entities:
- {entity: import, shows: [Source, Proposed session, Suggested activity type], collects: [Proposed session]}
- {entity: activity-type, shows: [Name]}
entryPoints:
- web: /profile?tab=imports
references:
- kind: code
  role: implementation
  target: frontend/src/components/imports/ImportsTab.tsx
- kind: code
  role: implementation
  target: frontend/src/components/imports/ImportRow.tsx
---

# Imports

Profile › Imports: the queue of pending imports with their proposed sessions.
