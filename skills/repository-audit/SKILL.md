---
name: repository-audit
description: Audit a software repository before planning or implementing changes. Use for unfamiliar codebases, migrations, refactors, architecture changes, risky fixes, or any task that requires evidence about repository structure, commands, constraints, ownership, secrets exposure, and verification coverage.
---

# Repository Audit

Build an evidence-backed map of the repository before proposing changes. Keep the audit proportional to the task and do not mutate files during the audit.

## Workflow

1. Read repository-local instructions completely, including `AGENTS.md`, `CLAUDE.md`, contributing guides, and relevant nested instructions.
2. Inspect the worktree status and preserve unrelated user changes.
3. Map the smallest relevant architecture: entry points, boundaries, data flow, persistence, tests, and deployment configuration.
4. Identify authoritative install, run, lint, type-check, test, and build commands from project files or CI. Do not invent commands.
5. Search for risks relevant to the request: secrets, generated files, migrations, public interfaces, destructive scripts, permission changes, and external side effects.
6. Inspect tests and CI to determine what they actually cover. Treat missing or indirect coverage as unverified.
7. Produce the audit report below. Separate observed facts from inferences and unresolved questions.

## Required Report

### Scope

- Requested outcome
- Repository and branch
- Local instructions applied

### Architecture

- Relevant components and responsibilities
- Call and data flow
- Boundaries that the change must preserve

### Commands

- Install
- Run
- Lint or format
- Type-check
- Test
- Build

Use `not found` when the repository provides no authoritative command.

### Risks

- Data-loss or destructive operations
- Secrets or private information
- Compatibility and migration concerns
- External systems or permissions

### Verification

- Existing evidence and coverage
- Checks required after implementation
- Remaining unknowns

### Recommendation

- Files or areas likely to change
- Safest implementation sequence
- Decisions that require user input

## Guardrails

- Do not expose secret values; report only file paths and secret categories.
- Do not treat README claims as proof when code, configuration, or CI contradicts them.
- Do not propose deleting, merging, or rewriting history until identity and recoverability are verified.
- Do not claim completion from a narrow test when the requested behavior is broader.
