# Architecture Standards

## Dependency direction

Prefer a one-way dependency flow:

`UI → controller/application service → domain → repository or external adapter`

Framework and transport details stay at the edges.

## Frontend

- Components render state and dispatch user intent.
- Hooks coordinate UI state but do not call external APIs directly.
- Controllers or application services orchestrate use cases.
- API clients handle transport concerns only.
- Domain rules remain testable without rendering UI.

## Backend

- Controllers translate transport input and output.
- Application services orchestrate use cases.
- Domain code owns business invariants.
- Repositories own persistence access.
- External adapters isolate third-party integrations.

## Exceptions

Document any deliberate exception with its reason, scope, and removal criteria. Do not introduce a new layer solely to satisfy naming; preserve a repository's established equivalent boundary when it has the same responsibility.
