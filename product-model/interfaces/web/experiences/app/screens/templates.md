---
entities:
- {entity: strength-template, shows: [Name, Exercises], collects: [Name, Exercises]}
- {entity: exercise, shows: [Name]}
entryPoints:
- web: /templates
references:
- kind: code
  role: implementation
  target: frontend/src/pages/TemplatesPage.tsx
---

# Templates

The template library and its editor.
