# AI-Brains System — Roadmap

## Goal
Build a global AI system that:

- stores full project context
- provides instant state awareness
- synchronizes ChatGPT ↔ Cursor workflows

---

## Strategic direction (MCA AI.Pack)

1. **Main Brain** (`AI-brains`) is the **control layer** for MCA AI.Pack — not an optional doc folder.
2. **MetaCODE mission** is part of the system; see [metacode-mission.md](metacode-mission.md).
3. **Lifecycle logging** is **mandatory** for major system and project changes (see standard below).
4. **Project registry** is **mandatory** for active projects (see standard below).
5. **Git safety** is required at major checkpoints (see standard below).
6. **SAFE UNKNOWN MODE** is a **core anti-hallucination rule**: do not invent facts; mark unknowns explicitly.
7. **Gulp Starter** is **paused** until Main Brain lifecycle controls are finalized.
8. **Next possible product direction:** **MetaBOT** (after the lifecycle layer is stable).

---

## Current Priority — Main Brain Lifecycle Layer

The current priority is to harden Main Brain before continuing implementation work in projects.

Main Brain must control:

- project registry
- lifecycle logs
- Git safety checkpoints
- rule precedence
- SAFE UNKNOWN behavior
- workflow trackers
- future project brains
- WebGPT Memory Module (`system/webgpt-memory-module.md`)

Additional system requirements for WebGPT and reconstructability:

- WebGPT Memory Module is now a core component
- Chat-to-chat migration must use system memory
- Project lifecycle must be reconstructable from logs

This stage is required before scaling to:

- gulp-starter development
- LAE implementation
- MetaBOT
- client/project-specific AI brains

---

## System references (lifecycle layer)

Paths are from the `AI-brains` repository root:

- `system/metacode-mission.md` — [MetaCODE mission](metacode-mission.md)
- `system/ai-lifecycle-log-standard.md` — [AI lifecycle log standard](ai-lifecycle-log-standard.md)
- `system/project-registry-standard.md` — [Project registry standard](project-registry-standard.md)
- `system/git-safety-standard.md` — [Git safety standard](git-safety-standard.md)
- `system/project-registry.md` — [Project registry](project-registry.md)
- `logs/lifecycle-log.md` — [Lifecycle log](../logs/lifecycle-log.md)
- `system/rule-precedence.md` — [Rule precedence](rule-precedence.md)
- `system/wiring-task-standard.md` — [Wiring task standard](wiring-task-standard.md)
- `system/webgpt-memory-module.md` — [WebGPT Memory Module](webgpt-memory-module.md)

---

## Stage 1 — Structure (DONE)

D:\AI\
- AI-brains
- projects
- tools
- workspace

---

## Stage 2 — Project Context

Each project must contain:

- roadmap
- current state
- next steps
- rules

---

## Stage 3 — Navigation System (CRITICAL)

Module: project-state

Functions:
- current stage tracking
- completion status
- next actions

---

## Stage 4 — Bridge System (CRITICAL)

ChatGPT → prompt → Cursor

Goal:
- short input → full project context

---

## Stage 5 — Standardization

All projects must follow:

- same structure
- same workflow
- same stages

---

## Stage 6 — Auto Context Injection

On project start:

AI must receive:
- roadmap
- current state
- last actions

---

## Stage 7 — Scaling

- multiple projects
- unified control
- centralized logic

---

## Core Principle

AI must ALWAYS know:
- where it is
- what it is doing
- what it is allowed to do

---

## Next Step

1. Finalize Main Brain lifecycle layer (registry, logs, Git checkpoints, rule precedence, SAFE UNKNOWN).
2. Update per-project roadmaps and project-state when work resumes outside Main Brain.
3. Choose next build focus after controls are stable: likely **MetaBOT**, or **gulp-starter** when unpaused.
4. Implement bridge prompts (ChatGPT → Cursor) once context files are mandatory across projects.

---

## MCA AI.Pack Missing Layers Roadmap

### Purpose

Track missing or incomplete layers required to evolve MCA AI.Pack into a full multi-agent system.

### Layer Status Table

| Layer | Current status | Current assets | Needed next |
|------|----------------|----------------|-------------|
| Control Layer | active | Main Brain v2 | continue hardening |
| Planning Layer | draft | planning-layer.md | create MB-Planner-v1 |
| Agent Layer | active foundation | agent-standard.md, agent-registry.md, MB-FlyCheck-v1 | create Factory Engineer and next agents |
| Tool Layer | not formalized | Git, Cursor, n8n, filesystem used manually | create tool-registry.md |
| Memory Layer | active foundation | lifecycle-log.md, project-registry.md, WebGPT Memory spec, Self-Describe | implement stronger migration prompts |
| State Layer | partial | project-registry.md, agent-registry.md, workflow trackers | create state-layer.md |
| Runtime Layer | partial / external | Cursor, n8n, manual execution | create runtime-layer.md later |
| Guardrails Layer | active foundation | FlyCheck, system-signals.md, SAFE UNKNOWN | expand validators |
| Observability Layer | partial | lifecycle-log.md, FlyCheck reports | create observability-layer.md |
| Policy Layer | active | rule-precedence.md, self-update-rules.md, agent-standard.md | continue enforcing |
| Human Layer | active | user approval, Cursor prompts, Git checkpoints | keep manual approval for critical changes |

### Priority Order

1. Planning Layer
2. Factory Engineer
3. Tool Layer
4. State Layer
5. Observability Layer
6. Runtime Layer

### Rules

- Do not build all layers at once.
- Each layer must have:
  - system specification
  - registry or status source if needed
  - at least one responsible agent if needed
  - lifecycle log entry when implemented
- Missing layer docs are roadmap items, not active systems.
- Registry and lifecycle must remain source of truth.