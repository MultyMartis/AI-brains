# Rule Precedence

This file defines the priority order for AI agents working inside the MCA AI.Pack frontend workflow.

## Priority order

1. User task in the current chat
2. Project workflow tracker
3. Project state files
4. Local project AGENTS.md / .cursorrules
5. Global AI-brains rules
6. Generic assistant knowledge

## Core rule

Never guess missing project context.

If something is unknown:

- Do NOT invent design, layout, assets, or values
- Do NOT simulate pixel-perfect implementation

Instead:

If task allows structural work:
- proceed with safe structure-only implementation

If task requires real design data:
- mark as UNKNOWN
- STOP and request input

## SAFE UNKNOWN MODE

When design source or required data is UNKNOWN:

Allowed:
- semantic HTML structure
- BEM class naming
- section skeletons
- placeholder content (clearly marked)
- safe layout containers (no exact spacing)

Forbidden:
- pixel-perfect spacing
- exact sizes
- color decisions
- typography decisions
- invented assets (images/icons)
- guessing layout from context

Goal:
Allow progress without hallucination.

## Task boundaries

### LAE / Analysis task
Allowed:
- analyze layout
- identify sections
- define UNKNOWNs
- create implementation plan

Forbidden:
- write code
- edit project files

### Block Implementation task
Allowed:
- create or edit one section HTML file
- create or edit one matching SCSS section file

Forbidden:
- edit pages
- edit style.scss
- edit scripts
- edit assets
- edit other sections
- wire the block into the project

### Wiring task
Allowed:
- connect an existing section to a page
- connect an existing SCSS file to style.scss
- connect an existing JS module to main.js if explicitly required

Forbidden:
- create new section layout
- redesign existing code
- refactor architecture
- edit unrelated files

### QA task
Allowed:
- run build
- check include paths
- check SCSS imports
- check JS init
- report errors

Forbidden:
- fix errors unless explicitly requested

## Conflict resolution

If Block Implementation v2 conflicts with normal Gulp requirements, Block Implementation v2 wins for the block task.

Required Gulp wiring must be done later as a separate Wiring task.

## Multi-file operations

All multi-file operations must be executed via Cursor/Codex prompts.

Manual editing is not allowed for:
- project structure
- mass changes
- page generation
- wiring batches

## Stop rule

After each task, stop and report:
- files changed
- files not changed
- build status if checked
- next recommended task
