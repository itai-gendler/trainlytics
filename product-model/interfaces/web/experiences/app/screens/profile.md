---
entities:
- {entity: athlete, shows: [Display name, Birth year, Experience level, Training goals, Injury notes, Coach notes, AI provider], collects: [Display name, Birth year, Experience level, Training goals, Injury notes, Coach notes, AI provider, AI key]}
entryPoints:
- web: /profile
references:
- kind: code
  role: implementation
  target: frontend/src/pages/ProfilePage.tsx
---

# Profile

Profile › Settings: about the Athlete, training goals, notes for the AI coach, and the AI provider and key.
