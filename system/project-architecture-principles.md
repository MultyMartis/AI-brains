# Project Architecture Principles

## Core Separation Logic

We separate system layers strictly:

1. Tool-level (project)
   Example: gulp-starter
   Purpose: implementation, build system, frontend development

2. Workflow-level (engine)
   Example: LAE (Layout Analysis Engine)
   Purpose: governs how implementation is performed

3. Meta-level (AI-brains)
   Location: D:\AI\AI-brains
   Purpose: global memory, navigation, orchestration across all projects

---

## Mapping Rules

- LAE roadmap → belongs to gulp-starter
- Gulp starter roadmap → belongs to gulp-starter
- AI-brains roadmap → belongs ONLY to AI-brains system

---

## Critical Rule

NEVER mix layers.

- Do NOT store global system logic inside project repos
- Do NOT store project-specific logic inside AI-brains core system

---

## Goal

Ensure that any AI agent always understands:

- where it is working
- what layer it belongs to
- what it is allowed to modify
