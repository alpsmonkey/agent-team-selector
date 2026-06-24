---
name: agent-team-selector
description: Select the smallest effective subagent/agent team for a project request. Use when the user asks to start, plan, scaffold, build, debug, refactor, migrate, release, or review a project with multiple agents/subagents, wants an optimal agent combination, wants lower-bug execution, or asks which agents should collaborate for frontend, backend, full-stack, data, DevOps, documentation, security, performance, QA, migration, or product work.
---

# Agent Team Selector

Recommend a focused subagent team before project execution. Optimize for speed, correctness, and low bug rate by selecting only agents that materially improve the outcome.

## Workflow

1. Parse the user's request for project type, deliverables, implementation scope, risk, technology stack, unknowns, and validation needs.
2. Classify the request as small, medium, large, or high-risk.
3. Read `references/team-presets.md` when the request matches a common pattern.
4. Read `references/selection-rules.md` for mixed-scope, ambiguous, or risk-heavy requests.
5. Read `references/subagent-library.md` when a broad or custom role selection is needed.
6. Recommend the smallest effective team; avoid recommending every plausible specialist.
7. Provide execution order and a ready-to-use coordination prompt.

## Default Bias

- Prefer `planner`, `coder`, and `reviewer` for most implementation tasks.
- Add `tester` when behavior, business logic, integration, UI, data, or regression risk exists.
- Add `architect` when the work crosses modules, changes boundaries, introduces migrations, or affects long-term structure.
- Add specialist agents only when their domain materially affects correctness or delivery risk.
- Use `main` as the coordinating role when outputting the final prompt, even if it is not listed as a worker.

## Output Format

Return these sections:

1. **Recommended Agent Team**: selected agents with one-line responsibilities.
2. **Why This Team**: concise rationale tied to the user's request.
3. **Execution Order**: ordered collaboration flow from analysis to final review.
4. **Agents Not Selected**: only mention notable omissions when they might be expected.
5. **Suggested Prompt**: a paste-ready Chinese prompt that asks Codex to use the recommended agents.

## Guardrails

- Keep small tasks small: 2-3 agents are usually enough.
- Keep medium implementation tasks to 3-5 agents unless clear risk justifies more.
- Use 6-8 agents only for full-stack, production, security-sensitive, migration, or release-heavy work.
- Do not imply that subagents are truly available in the runtime; phrase the output as a recommended team unless the current Codex environment exposes actual subagent tools.
- If the request is too vague, state assumptions and provide a provisional team instead of blocking.

