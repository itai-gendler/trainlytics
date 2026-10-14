---
entities:
- {entity: cardio-session, shows: [Date, Title, Segments, Total duration, Average heart rate, Calories]}
- {entity: strength-session, shows: [Date, Title, Exercises, Duration, Calories]}
- {entity: daily-steps, shows: [Date, Steps]}
entryPoints:
- web: /stats?tab=history
references:
- kind: code
  role: implementation
  target: frontend/src/pages/HistoryPage.tsx
---

# History

Stats › History: this week's minutes and calories, weekly trends with steps, AI insights, and every logged session newest first.
