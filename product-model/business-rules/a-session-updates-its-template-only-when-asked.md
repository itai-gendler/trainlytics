---
appliesTo:
- type: capability
  id: log-session
- type: entity
  id: strength-template
  effect: changes
references:
- kind: code
  role: implementation
  target: frontend/src/lib/strengthSession.ts#computeDiff
- kind: code
  role: implementation
  target: frontend/src/lib/hooks/useStrengthSessionForm.ts#useStrengthSessionForm
---

# A session updates its template only when the Athlete says so

When a session started from a template differs in its exercises or sets, the Product lists the differences and asks; the template changes only if the Athlete confirms. Set notes and set effort never go to the template.
