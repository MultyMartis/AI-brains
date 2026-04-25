# MCA AI Terminology Map

## Purpose
Provide mapping between MCA internal terms and industry-standard terminology.

This file ensures:
- alignment with external AI ecosystem
- clarity for new agents
- safe future refactoring

---

## Core System Terms

| MCA Term | Standard Term | Description |
|----------|--------------|-------------|
| Main Brain | Supervisor / Orchestrator | Central control system managing agents and workflows |
| AI-brains | Knowledge Base / Control Layer | Canonical system rules, memory, and architecture |
| MCA AI.Pack | Multi-Agent System | Full system of agents and workflows |
| Project Brain | Project Context / Subsystem | Per-project controlled context |

---

## Agent System

| MCA Term | Standard Term | Description |
|----------|--------------|-------------|
| Agent | Agent | AI unit performing defined task |
| Engineer Agent | Architect Agent / Engineering Agent | Designs and improves system |
| Factory Engineer | System Architect | Main engineering agent |
| Subagent | Specialist Agent | Narrow-purpose agent |
| Agent Registry | Agent Registry / Catalog | Source of truth for agents |

---

## Control & Validation

| MCA Term | Standard Term | Description |
|----------|--------------|-------------|
| FlyCheck | Guardrail / Validator | System consistency and health check |
| System Signals | Guardrails / Signals | Warning and integrity indicators |
| SAFE UNKNOWN | Safe Fallback | Controlled handling of missing data |

---

## Memory & Context

| MCA Term | Standard Term | Description |
|----------|--------------|-------------|
| Self-Describe | Introspection / System Context | System self-description mechanism |
| WebGPT Memory | Context Persistence | Cross-session context restoration |
| Lifecycle Log | Event Log | System change history |
| Project Registry | System Registry | Project-level tracking |

---

## Execution & Workflow

| MCA Term | Standard Term | Description |
|----------|--------------|-------------|
| Cursor execution | Tool execution | External execution layer |
| Prompt | Instruction | Task definition for agent |
| Agent workflow | Execution pipeline | Step-by-step agent logic |
| Handoff | Delegation | Transfer of task between agents |

---

## Rules

- MCA internal terms are PRIMARY
- Standard terms are reference only
- Do NOT rename system components automatically
- Terminology map is used for:
  - documentation
  - onboarding
  - external alignment

---

## Naming Model

MCA uses a dual-layer naming system:

| Field | Meaning |
|------|--------|
| id | internal unique identifier |
| name | human-readable name |
| standard_name | industry equivalent |
| type | entity type |
| owner_system | controlling system |
| status | lifecycle state |

Purpose:

- keep internal clarity
- stay compatible with external ecosystems
