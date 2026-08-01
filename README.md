# Agent Engineering Kit

A reusable, tool-neutral playbook for AI-assisted software engineering with Codex, Claude, and compatible coding agents.

## Contents

- `agents/` — repository instruction templates.
- `standards/` — architecture and delivery rules.
- `templates/` — implementation-plan and completion-report formats.

## Core principles

1. Repository-local instructions remain authoritative.
2. Agents inspect the current architecture before editing.
3. UI hooks and components do not call external APIs directly; requests pass through the project's controller or application-service boundary.
4. Every change has a plan proportional to its risk.
5. Completion requires tests, checks, and an evidence-based report.
6. Secrets and private project data are never copied into public artifacts.

## Adoption

Copy the relevant templates into a project, then adapt commands and architecture rules to that repository. A link to this kit alone is not a substitute for a local `AGENTS.md` or `CLAUDE.md`.
