# AGENTS.md

## Project

Describe the product, primary stack, runtime versions, and repository boundaries.

## Commands

- Install: `<authoritative install command>`
- Run: `<authoritative run command>`
- Lint: `<authoritative lint command>`
- Type-check: `<authoritative type-check command>`
- Test: `<authoritative test command>`
- Build: `<authoritative build command>`

Remove commands the repository does not provide. Never invent a command.

## Architecture

- Read the existing architecture before changing boundaries.
- UI hooks and components must not call external APIs directly.
- Route network operations through the project's controller or application-service layer.
- Keep transport, orchestration, domain logic, and persistence responsibilities separate.
- Do not modify deployed migrations unless the task explicitly requires a migration strategy.

## Workflow

1. Inspect relevant instructions, code, tests, and current worktree state.
2. Write a proportional implementation plan.
3. Preserve unrelated user changes.
4. Implement the smallest complete solution that satisfies the requested outcome.
5. Run the relevant checks.
6. Report changed files, verification evidence, and remaining risks.

## Safety

- Never commit secrets, credentials, private customer data, or local environment files.
- Confirm exact targets before destructive operations.
- Do not claim completion when verification is missing or indirect.
