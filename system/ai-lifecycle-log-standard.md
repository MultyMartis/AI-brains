# AI Lifecycle Log Standard

## Purpose

The AI Lifecycle Log records the life of the MCA AI.Pack system.

It must show:
- what was changed
- why it was changed
- which project or system area was affected
- who/what executed the change
- whether Git was updated

## Scope

Lifecycle logging applies to:

- AI-brains changes
- new project creation
- project workflow changes
- roadmap changes
- prompt pack changes
- system rule changes
- major architectural decisions

## Log location

Global system log:

D:\AI\AI-brains\logs\lifecycle-log.md

Per-project log:

<project_root>\docs\ai-system\lifecycle-log.md

## Required log entry format

Each entry must use this format:

## YYYY-MM-DD — Short title

- scope:
- affected_area:
- files_changed:
- reason:
- executed_by:
- git_status:
- next_action:

## Rules

- Every system-level change must be logged.
- Every new project must be registered.
- Every roadmap change must be logged.
- Every Git commit must be referenced in the log.
- Logs must be written before moving to the next major task.

## Forbidden

Do not log:
- secrets
- passwords
- API keys
- private client credentials
