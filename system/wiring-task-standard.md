# Wiring Task Standard

This standard defines how AI agents connect already-created frontend blocks into a Gulp project.

## Purpose

A Wiring task connects existing files into the project build graph.

It must not create new design, layout, content, or architecture.

## When to use

Use Wiring task after Block Implementation when a section already exists but is not yet visible or not yet styled.

## Allowed files

Depending on the task, only these files may be edited:

- src/pages/*.html
- src/scss/style.scss
- src/js/main.js
- src/partials/layout/scripts.html only if explicitly required

## Forbidden actions

Do not:
- create new sections
- rewrite existing sections
- edit unrelated SCSS
- edit base/layout/component layers
- edit dist
- add libraries without explicit approval
- invent assets
- rename files
- move files

## Required checks before editing

Before wiring, verify:

1. Section HTML file exists
2. Section SCSS file exists
3. Page target is clear
4. SCSS entry file is clear
5. JS module exists if JS wiring is requested

If any item is missing, report UNKNOWN and stop.

## Required output after wiring

Report:

- page include added or already present
- SCSS import/use added or already present
- JS import/init added or skipped
- files changed
- build command result if executed

## Safety rule

One Wiring task should connect one section or one clearly defined group of files.

Do not wire the whole page unless explicitly requested.

## Dependency rule

Wiring must not assume that a block is final.

If block was created in SAFE UNKNOWN MODE:
- wiring is allowed
- but must not imply visual completeness
