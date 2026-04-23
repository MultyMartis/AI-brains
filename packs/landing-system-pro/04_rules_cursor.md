# Landing System PRO — Cursor / IDE Rules

## Local git first

- **Repo initialized** (or clone) before substantive work.
- **Branch per task or per pass**: `task/<slug>` for a block or bugfix; `pass/<slug>` for a full-page pass (e.g. `pass/mobile`). See `05_git_workflow.md`.
- **Commit when the build is green** — small, descriptive messages. If the tree is dirty before a new pass, **commit or stash** intentionally.

## One task, one scope

- Implement **exactly** the user’s task — one block, one pass, or one enhancement.
- **No random refactors**, no formatting sweeps in unrelated files, no renames across the codebase unless the task says so.
- **Do not edit `dist/`** — run the Gulp/npm build and fix **`src/`** only.

## Mandatory build check

- After **any** change that can affect HTML/CSS/JS output: run the project’s **build script** (commonly `npm run build`). Fix errors **in source**.
- Do not mark a task done with a **failing build**.

## Standard loop

1. Read task + open **only** needed `src/` files.
2. Implement with **BEM** and **scoped** section SCSS.
3. **Build** → fix **src/** until clean.
4. **Commit** on the task/pass branch with a message that names block + phase.
5. **Report**: files touched, command + result, how to verify (viewports), follow-ups.

## Includes and SCSS graph

- After moving/renaming partials: verify **HTML includes** and **`@import` / `@use` order** per starter conventions.
- Keep import order stable: **tokens/variables → mixins → base → layout → blocks** (adjust names to your starter).

## Safety

- Follow **`cursor/cursor-safety-rules.txt`** for deps, deletes, and secrets.
- If a change might spill into another section: **stop** and ask for a narrower task.

## ChatGPT vs Cursor

- **ChatGPT**: order of blocks/passes and **scoped** generated fragments.
- **Cursor**: **files**, **build**, **git**, **include graph**, **BEM in the actual codebase**.
- System prompt: **`cursor/cursor-system-prompt.txt`**.
