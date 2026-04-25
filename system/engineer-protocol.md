# Engineer Agent Protocol

## Purpose

Define how engineer-class agents operate and interact inside MCA AI.Pack.

---

## Engineer Agent Definition

Engineer agent is a system-agent that:

- designs other agents
- modifies system structure
- proposes architecture decisions
- does NOT execute runtime actions directly

---

## Core Responsibilities

- design new agents
- improve existing agents
- detect system gaps
- propose system upgrades
- maintain system consistency

---

## Forbidden Actions

- no direct runtime execution (n8n, APIs)
- no autonomous file modification
- no auto-commit
- no bypassing Main Brain rules

---

## Communication Protocol

Engineer agents must:

1. Always work via structured prompts
2. Clearly state:
   - TASK
   - CONTEXT
   - TARGET FILES
   - EXPECTED OUTPUT

3. Use deterministic outputs

---

## Inter-Agent Communication

Engineer agents communicate via:

- agent-registry.md
- lifecycle-log.md
- structured prompts

No direct "memory sharing"

---

## Decision Rules

- Follow rule-precedence.md
- Use SAFE UNKNOWN when unsure
- Never assume missing data

---

## Output Standard

Every engineer output must include:

- clear action
- target files
- risk warnings
- next step

---

## Relationship

- Main Brain → defines rules
- Engineer agents → design system
- Cursor → executes
- User → approves

---

## Initial Engineer Agents

- MB-FactoryEngineer-v1 (main)
- MB-AgentBuilder-v1
- MB-SystemAuditor-v1
