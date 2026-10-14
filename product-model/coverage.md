---
scope: The Trainlytics web app and the FastAPI backend behind it.
method: Static reading of source, README, specs and changelog at the pinned commit; nothing was run.
covered:
- description: Backend API routers for sign-in, sessions, templates, plans, steps, settings, imports, integrations, AI and analytics.
  paths:
  - backend/app/api/__init__.py
  - backend/app/api/auth.py
  - backend/app/api/sessions.py
  - backend/app/api/templates.py
  - backend/app/api/plans.py
  - backend/app/api/plan_summary.py
  - backend/app/api/steps.py
  - backend/app/api/exercises.py
  - backend/app/api/exercise_types.py
  - backend/app/api/cardio_types.py
  - backend/app/api/profile.py
  - backend/app/api/imports.py
  - backend/app/api/strava.py
  - backend/app/api/apple_health.py
  - backend/app/api/ai.py
  - backend/app/api/analytics.py
- description: Backend services, models, schemas, settings and authentication.
  paths:
  - backend/app/services/
  - backend/app/models/
  - backend/app/schemas/
  - backend/app/auth.py
  - backend/app/config.py
  - backend/app/dependencies.py
  - backend/app/main.py
  - backend/app/database.py
  - backend/app/__init__.py
- description: Frontend pages, components, hooks and client logic of the signed-in app and sign-in page.
  paths:
  - frontend/src/App.tsx
  - frontend/src/main.tsx
  - frontend/src/contexts/
  - frontend/src/lib/
  - frontend/src/components/
  - frontend/src/pages/AnalyticsPage.tsx
  - frontend/src/pages/CardioSessionDetailPage.tsx
  - frontend/src/pages/HistoryPage.tsx
  - frontend/src/pages/LoginPage.tsx
  - frontend/src/pages/LogWorkoutPage.tsx
  - frontend/src/pages/PlanPage.tsx
  - frontend/src/pages/ProfilePage.tsx
  - frontend/src/pages/SettingsPage.tsx
  - frontend/src/pages/StatsPage.tsx
  - frontend/src/pages/StepsPage.tsx
  - frontend/src/pages/StrengthSessionDetailPage.tsx
  - frontend/src/pages/TemplatesPage.tsx
  - frontend/src/pages/TodayPage.tsx
  - frontend/src/pages/WorkoutModePage.tsx
exclusions:
- description: Database migrations and their history.
  paths:
  - backend/migrations/
  - backend/alembic.ini
- description: Backend and frontend test suites.
  paths:
  - backend/tests/
  - frontend/src/__tests__/
  - frontend/src/test-setup.ts
- description: Local-development demo account seeding.
  paths:
  - backend/app/demo/
  - scripts/seed-demo.sh
- description: Developer SQL console router, enabled only by a debug environment flag.
  paths:
  - backend/app/api/debug.py
- description: Build, container, web server and deployment configuration.
  paths:
  - backend/Dockerfile
  - backend/pyproject.toml
  - backend/uv.lock
  - frontend/Dockerfile
  - frontend/nginx.conf
  - frontend/package.json
  - frontend/pnpm-lock.yaml
  - frontend/vite.config.ts
  - frontend/eslint.config.js
  - frontend/tsconfig.json
  - frontend/tsconfig.app.json
  - frontend/tsconfig.node.json
  - frontend/scripts/
  - docker-compose.yml
  - docker-compose.prod.yml
  - scripts/deploy.sh
  - .env.example
  - backend/.dockerignore
  - backend/.python-version
  - frontend/.dockerignore
  - frontend/.npmrc
- description: Styling, static assets, web manifest and the HTML shell.
  paths:
  - frontend/src/index.css
  - frontend/src/assets/
  - frontend/public/
  - frontend/index.html
  - logo.png
- description: Unrouted activity types page superseded by the Settings section.
  paths:
  - frontend/src/pages/CardioTypesPage.tsx
unmapped:
- description: AI request log shown in the Profile page's debug section, and its SQL runner.
  paths:
  - backend/app/models/ai_request_log.py
  - frontend/src/components/analytics/SqlDebugModal.tsx
limitations: []
---

# Coverage
