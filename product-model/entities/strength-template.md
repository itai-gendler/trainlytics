---
domain: templates
references:
- kind: code
  role: implementation
  target: backend/app/models/template.py#StrengthTemplate
- kind: code
  role: implementation
  target: backend/app/services/template_versioning.py#_write_template_history
---

# Strength template

A reusable strength workout: a name and exercises with their sets, used to prefill a session and to plan one.

## Information kept

- **Name** — the template's name
- **Exercises** — the ordered exercises, each with numbered sets of reps and weight in kg
- **Version** — starts at 1 and goes up each time the exercises or sets change
- **Version history** — the exercises and sets of every version, so a planned session can be compared with the version it was planned with
