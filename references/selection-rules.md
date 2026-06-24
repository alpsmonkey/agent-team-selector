# Selection Rules

Use these rules after classifying the user request. Prefer the smallest team that covers the major failure modes.

## Baseline

- Add `planner` for any project request with more than one step.
- Add `coder` when implementation, file edits, scaffolding, or configuration changes are required.
- Add `reviewer` when the request produces code, architecture, docs, release steps, or any durable artifact.
- Add `tester` when correctness depends on behavior, edge cases, integrations, UI, data, or regressions.
- Add `main` only in the final coordination prompt as the role that integrates outputs.

## Complexity

- Small: one file, simple config, text-only, or obvious local change. Use 2-3 agents.
- Medium: multiple files, one feature area, typical tests, known stack. Use 3-5 agents.
- Large: full-stack, new app, cross-module change, migration, release, or unclear scope. Use 5-8 agents.
- High-risk: auth, security, money, personal data, data loss, production release, migrations, or scale concerns. Add the relevant risk specialist.

## Add Specialists

- Add `architect` for cross-module design, long-term structure, migrations, new systems, APIs with multiple consumers, or unclear boundaries.
- Add `researcher` for external docs, unfamiliar libraries, API behavior, model/provider choices, or product comparisons.
- Add `codebase-explorer` for existing projects when structure, conventions, or ownership are unknown.
- Add `requirements-analyst` when the request is vague, acceptance criteria are unclear, or scope may expand.
- Add `debugger` for failures, flaky tests, regressions, crashes, or bug reports.
- Add `log-analyst` when logs, stack traces, monitoring data, or production incidents are central.
- Add `product` for feature definition, prioritization, workflows, user value, or scope tradeoffs.
- Add `ux-designer` for forms, flows, dashboards, editor tools, onboarding, and state-heavy UI.
- Add `ui-designer` for visual polish, layout, design-system consistency, or brand-sensitive surfaces.
- Add `accessibility` for public UI, forms, navigation, keyboard interaction, or compliance-sensitive products.
- Add `frontend` for browser UI, component logic, state, styling, and responsive behavior.
- Add `browser-tester` when visual correctness or interaction must be verified in a browser.
- Add `backend` for server logic, APIs, jobs, permissions, or business rules.
- Add `api-designer` when API contracts, clients, versioning, or error models matter.
- Add `database` for schema, migrations, queries, indexes, data integrity, or reporting data.
- Add `auth` for login, permissions, sessions, tokens, organizations, roles, or account security.
- Add `integration` for third-party APIs, webhooks, queues, retries, and external data exchange.
- Add `security` for auth, permissions, secrets, uploads, payments, user input, sensitive data, or public endpoints.
- Add `performance` for latency, scaling, memory, CPU, rendering, caching, database load, or batch volume.
- Add `reliability` for production services, concurrency, retries, idempotency, graceful degradation, and failure recovery.
- Add `observability` for production diagnostics, logs, traces, metrics, and alerts.
- Add `devops` for CI/CD, deployment, containers, build pipelines, and environment configuration.
- Add `release-manager` for production rollout, rollback, migration order, and release notes.
- Add `docs` when setup, usage, APIs, migrations, or user-facing behavior changes.

## Avoid Over-Selection

- Do not add `architect` for tiny edits unless structure is the issue.
- Do not add `security` just because every project benefits from security; require a concrete risk surface.
- Do not add `performance` without a performance-sensitive path or measurable concern.
- Do not add framework specialists when a generic `frontend` or `backend` agent is enough.
- Do not add `devops` unless build, deployment, CI/CD, environments, or release flow matter.
- Do not add both `qa` and `tester` unless the task needs separate manual test planning and automated validation.

## Tie Breakers

- If two agents overlap, choose the one closest to the main risk.
- If the project is early-stage, prefer `product`, `planner`, and `architect` before implementation specialists.
- If the project already exists, prefer `codebase-explorer` before `architect` when local conventions are unknown.
- If the user asks for speed, reduce specialists and keep `reviewer`.
- If the user asks for low bugs, keep `tester` and `reviewer`, then add the most relevant risk specialist.

