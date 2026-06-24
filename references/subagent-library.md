# Subagent Library

Use this library to choose roles. Select by contribution to correctness, speed, and risk reduction.

## Core

- `main`: Coordinate selected agents, resolve conflicts, integrate final recommendation or delivery plan.
- `planner`: Decompose goals, identify dependencies, sequence work, define validation checkpoints.
- `architect`: Evaluate system boundaries, module design, long-term maintainability, migration risk, and technical tradeoffs.
- `coder`: Implement code changes according to the chosen plan and existing project style.
- `tester`: Design and run verification, add or select tests, check regressions and edge cases.
- `reviewer`: Inspect final changes for bugs, missing tests, regression risk, maintainability, and requirement gaps.

## Discovery

- `researcher`: Find official docs, compare approaches, inspect unfamiliar APIs, and summarize external constraints.
- `codebase-explorer`: Map project structure, entry points, dependencies, ownership boundaries, and local conventions.
- `requirements-analyst`: Clarify scope, assumptions, acceptance criteria, non-goals, and ambiguous user needs.
- `debugger`: Reproduce bugs, narrow the failing path, inspect traces, and identify root cause.
- `log-analyst`: Analyze logs, stack traces, monitoring events, and runtime error patterns.

## Product And Design

- `product`: Evaluate user value, prioritization, workflow fit, feature boundaries, and product tradeoffs.
- `ux-designer`: Design flows, states, empty/error/loading behavior, interaction models, and usability details.
- `ui-designer`: Shape visual hierarchy, layout, component consistency, density, spacing, and polish.
- `accessibility`: Check keyboard flow, semantics, contrast, focus states, screen reader behavior, and inclusive UX.
- `content-designer`: Improve UI copy, labels, errors, empty states, onboarding text, and user-facing explanations.

## Frontend

- `frontend`: Implement UI components, pages, state management, styling, responsive behavior, and browser-facing logic.
- `react-specialist`: Handle React, Next.js, hooks, rendering behavior, component architecture, and hydration issues.
- `vue-specialist`: Handle Vue, Nuxt, composition API, reactive state, and component patterns.
- `mobile-ui`: Optimize responsive layout, touch interactions, small screens, and mobile-specific usability.
- `browser-tester`: Verify visual rendering, layout, interactivity, screenshots, console errors, and cross-viewport behavior.

## Backend

- `backend`: Implement services, APIs, business logic, job processing, and server-side behavior.
- `api-designer`: Design endpoint contracts, request/response models, errors, versioning, and client compatibility.
- `database`: Design schemas, migrations, indexes, queries, constraints, and data integrity checks.
- `auth`: Evaluate authentication, authorization, sessions, tokens, permissions, RBAC/ABAC, and account flows.
- `integration`: Handle third-party APIs, webhooks, queues, external services, retries, and data mapping.

## Quality And Risk

- `qa`: Produce manual test cases, edge scenarios, regression checklists, and acceptance validation.
- `security`: Check auth bypass, injection, XSS, CSRF, secrets, unsafe deserialization, uploads, payments, and sensitive data.
- `performance`: Analyze latency, CPU, memory, caching, rendering, database load, batch work, and scalability bottlenecks.
- `reliability`: Check timeouts, retries, idempotency, rate limits, graceful degradation, failure recovery, and concurrency hazards.
- `observability`: Ensure useful logs, metrics, traces, error reporting, alert signals, and diagnostic context.

## Infrastructure

- `devops`: Handle CI/CD, build scripts, deployment, environments, secrets management, and operational workflows.
- `cloud`: Review cloud resources, IAM, networking, storage, managed services, cost, and deployment constraints.
- `container`: Review Dockerfiles, compose files, image size, runtime dependencies, and container startup behavior.
- `release-manager`: Plan release steps, rollout, rollback, migration order, release notes, and production risk controls.
- `repo-maintainer`: Improve dependencies, scripts, project layout, linting, formatting, and repository hygiene.

## Documentation And Communication

- `docs`: Write or update README, setup guides, API docs, migration notes, and user/developer documentation.
- `technical-writer`: Convert complex technical content into clear, structured explanations.
- `changelog`: Produce change logs, release notes, upgrade notes, and user-facing summaries.
- `support`: Anticipate user support issues, FAQs, troubleshooting steps, and failure recovery guidance.

## Specialized

- `data-engineer`: Handle ETL, data pipelines, batch processing, data quality, warehouse flows, and data contracts.
- `ml-engineer`: Handle model calls, prompt flows, evaluation, inference behavior, embeddings, and AI pipeline quality.
- `analytics`: Design events, funnels, dashboards, metrics definitions, tracking plans, and reporting logic.
- `migration`: Plan and execute framework upgrades, database migrations, API migrations, or legacy replacement work.
- `localization`: Review languages, translations, time zones, date formats, currency, pluralization, and locale behavior.
- `legal-compliance`: Flag privacy, retention, licensing, consent, compliance, and policy-sensitive concerns.

