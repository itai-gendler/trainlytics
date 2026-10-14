---
entities:
- {entity: athlete, shows: [Rest timer length], collects: [Rest timer length]}
- {entity: activity-type, shows: [Name], collects: [Name]}
- {entity: exercise-type, shows: [Name], collects: [Name]}
- {entity: exercise, shows: [Name, Notes, Exercise types, Weight steps, Replacements], collects: [Name, Notes, Exercise types, Weight steps, Replacements]}
entryPoints:
- web: /settings
references:
- kind: code
  role: implementation
  target: frontend/src/pages/SettingsPage.tsx
---

# Settings

The rest timer, activity types, exercise types and the exercise library with weight steps and replacements.
