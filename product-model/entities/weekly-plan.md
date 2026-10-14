---
relations:
- {entity: planned-session, verb: holds, cardinality: one-to-many}
domain: plan
references:
- kind: code
  role: implementation
  target: backend/app/models/plan.py#WeeklyPlan
---

# Weekly plan

The Athlete's plan for one Monday-to-Sunday week.

## Information kept

- **Week start** — the Monday the week starts on; one plan per week
