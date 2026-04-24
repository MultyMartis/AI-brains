# WebGPT Memory Module

## Purpose

This module enables safe and lossless migration between WebGPT chats.

It reconstructs project and system context using Main Brain memory sources.

---

## Data sources

The module must use:

- lifecycle-log.md
- project-registry.md
- git history (if required)
- workflow-tracker.md (project level)
- project-state.md (project level)

---

## Capabilities

The module can generate:

1. Migration prompt (chat → new chat)
2. Project start prompt (new chat / new user)
3. Context reconstruction prompt
4. Handoff prompt (to another developer / agent)

---

## Rules

- Never guess missing data
- If context is incomplete → mark UNKNOWN
- Use SAFE UNKNOWN MODE when needed
- Prefer real logs over assumptions

---

## Migration flow

1. Identify project
2. Load registry entry
3. Load lifecycle log
4. Load workflow tracker
5. Extract current phase and state
6. Build migration prompt
7. Output structured prompt

---

## Output format

Migration prompt must include:

- project context
- current phase
- current task
- known decisions
- constraints
- next action

---

## Key principle

WebGPT is stateless.

Main Brain provides memory.
