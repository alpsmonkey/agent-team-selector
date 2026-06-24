# Team Presets

Use these presets as starting points. Add or remove agents based on request-specific risk.

## Tiny Change

Team: `coder`, `reviewer`
Use for copy edits, one-line fixes, simple config edits, or obvious local changes.

## Small Code Change

Team: `planner`, `coder`, `reviewer`
Use for focused implementation with low risk and limited scope.

## Bug Fix

Team: `debugger`, `coder`, `tester`, `reviewer`
Use for reproducible failures, regressions, broken tests, crashes, or incorrect behavior.

## New Feature

Team: `planner`, `architect`, `coder`, `tester`, `reviewer`
Use for user-facing or multi-file features with meaningful behavior.

## Existing Codebase Feature

Team: `codebase-explorer`, `planner`, `coder`, `tester`, `reviewer`
Add `architect` if boundaries or long-term structure are affected.

## Frontend App

Team: `product`, `ux-designer`, `frontend`, `accessibility`, `browser-tester`, `reviewer`
Add `react-specialist` or `vue-specialist` only when framework-specific complexity matters.

## Backend API

Team: `architect`, `backend`, `api-designer`, `database`, `security`, `tester`, `reviewer`
Remove `database` if no persistence is involved. Remove `security` only when no auth, user input, or sensitive data exists.

## Full-Stack App

Team: `product`, `architect`, `frontend`, `backend`, `database`, `tester`, `security`, `reviewer`
Add `browser-tester` for visual or interaction-heavy UI. Add `devops` for deployable production projects.

## Authentication Or Permissions

Team: `architect`, `auth`, `backend`, `security`, `tester`, `reviewer`
Add `frontend` if login, signup, account, or role UI is part of the request.

## Database Migration

Team: `architect`, `database`, `migration`, `tester`, `release-manager`, `reviewer`
Add `backend` when application code must change with the schema.

## Performance Issue

Team: `debugger`, `performance`, `coder`, `tester`, `reviewer`
Add `database` for query or storage bottlenecks. Add `browser-tester` for rendering or interaction jank.

## Production Release

Team: `tester`, `security`, `reliability`, `observability`, `devops`, `release-manager`, `reviewer`
Use for launch readiness, rollout plans, rollback plans, or production-sensitive changes.

## Documentation Task

Team: `researcher`, `docs`, `technical-writer`, `reviewer`
Add `changelog` for release notes or versioned changes.

## Data Pipeline

Team: `data-engineer`, `database`, `reliability`, `tester`, `observability`, `reviewer`
Add `analytics` if metrics, reporting, or tracking definitions are central.

## AI Or LLM Feature

Team: `product`, `ml-engineer`, `backend`, `tester`, `security`, `reviewer`
Add `data-engineer` for retrieval/data pipelines. Add `researcher` for provider/model/API decisions.

## Migration Or Upgrade

Team: `architect`, `migration`, `coder`, `tester`, `docs`, `release-manager`, `reviewer`
Add framework or infrastructure specialists only when the migration touches those domains.

