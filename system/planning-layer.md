# Planning Layer

## Purpose

Define how tasks are decomposed, planned, and prepared for execution within MCA AI.Pack.

The Planning Layer sits between incoming goals and execution: it produces structured plans, assignments, and handoff artifacts. It does not perform work that changes runtime state, the filesystem, or external systems.

---

## Planner Role

Planner is responsible for:

- Breaking high-level goals into concrete tasks and subtasks
- Defining ordered or parallelizable execution steps with clear inputs and outputs
- Assigning tasks to agents according to capability, load, and policy
- Estimating complexity (effort, risk, dependencies) to support scheduling and escalation

The Planner reasons over **registry** (available agents, tools, packs) and **system context** (constraints, policies, environment). When information is missing or ambiguous, the Planner applies **SAFE UNKNOWN**: treat unknowns explicitly, avoid guessing execution-critical facts, and surface assumptions as risks or validation items rather than silently filling gaps.

---

## Core Components

| Component | Responsibility |
|-----------|----------------|
| **Task Decomposer** | Maps goals to a tree or graph of subtasks; identifies dependencies and merge points |
| **Step Generator** | Turns subtasks into executable steps (preconditions, actions, success criteria, artifacts) |
| **Agent Selector** | Chooses agent(s) per step from the registry; respects roles, skills, and guardrails |
| **Validation Planner** | Plans checks before/after steps (lint, review gates, human approval, dry-run); aligns with risks |

---

## Planning Flow

1. **Receive high-level task** — Normalize the goal, scope, and acceptance criteria; ingest system context and registry entries relevant to the domain.
2. **Decompose into subtasks** — Use Task Decomposer; record dependencies and optional parallel branches.
3. **Define execution steps** — Use Step Generator; each step must be actionable and verifiable.
4. **Assign agents** — Use Agent Selector; document rationale when multiple agents are valid.
5. **Prepare execution prompts** — Produce handoff bundles (objectives, constraints, inputs, output schema, stop conditions) for downstream executors.

---

## Output Format

Planner must output a single structured plan that includes:

- **Task breakdown** — Hierarchical or graph view of subtasks with IDs and dependencies
- **Step list** — Ordered steps with inputs, expected outputs, and validation hooks
- **Assigned agents** — Per step: agent id (from registry), role, and any co-agent or reviewer
- **Risks** — Technical, operational, and compliance risks; mitigations where known
- **Next actions** — Immediate handoffs (who runs what next), blockers, and open questions tagged per SAFE UNKNOWN

---

## Rules

- **Must not execute tasks** — No shell commands, tool side effects, API mutations, or agent runs initiated by the Planning Layer output path alone.
- **Must not modify files** — Planning artifacts are proposals; filesystem and config changes belong to execution agents under separate control.
- **Must follow SAFE UNKNOWN** — Unknown capabilities, data shapes, or environment facts are declared; never fabricate registry entries or pretend context exists.
- **Must use registry and system context** — Plans cite which agents/tools/packs apply and which policies or limits bound the work.

---

## Future Agent

- **MB-Planner-v1** — Dedicated planner agent that implements this specification: consumes goals and context, emits the required output format, and hands off to executor agents without crossing execution boundaries.
