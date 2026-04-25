# MB-FlyCheck-v1

## Purpose

System stability verification agent.

## Description

Performs a fast check of critical system components:

- project-registry
- lifecycle-log
- agent-registry
- key system files

Detects:

- missing files
- inconsistencies
- outdated system state

## Usage

FlyCheck is a **read-only** workflow: an executor loads the registries and logs, runs the checks in `workflow.md`, and emits a **FLYCHECK REPORT**. There is no separate binary; consistency is enforced by following the same steps every time.

### Via Cursor (Ask mode)

1. Open **Ask** so the assistant stays read-only.
2. Point at this agent folder or paste `workflow.md`, then ask explicitly to **run FlyCheck** against `D:\AI\AI-brains` (or your repo root).
3. The model should load `project-registry`, `lifecycle-log`, and `agent-registry`, apply checks A–G, and print the report sections below.

### Via command prompt

There is no dedicated CLI. From the repo root you (or a script) **manually** open the same files FlyCheck references and verify them against `workflow.md`, or invoke your editor/AI with the same instructions as above. Optional: `type system\agents\MB-FlyCheck-v1\workflow.md` to review steps before auditing.

### Expected output format

The report must be titled **FLYCHECK REPORT** and include:

- **Status** — one of: `OK`, `WARNING`, `BROKEN`
- **Missing files** — paths that should exist but do not
- **Inconsistencies** — registry vs disk, registry vs lifecycle, agent-folder gaps, timestamp drift
- **Risks** — follow-on impact if left unfixed
- **Recommended actions** — concrete next steps (still no auto-fix inside FlyCheck)

Deterministic rule: same inputs and same workflow version → same classification of issues and same status bar logic (only ordering of equal-severity items may vary if listed as discovered).

## Status

active (v1 stable logic)
