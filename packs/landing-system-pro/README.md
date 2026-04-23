# Landing System PRO (LS PRO)

**Landing System PRO** is a **local workflow and knowledge pack** for shipping **commercial landing pages** and **standalone promo pages** with **HTML + SCSS + JavaScript**, a **Gulp** starter, **BEM**, and **section-by-section** work. **ChatGPT** controls *what* is generated (one block, one pass at a time). **Cursor** applies it to the repo, runs the **build**, and keeps **git** disciplined.

It is **not** a UI framework and **not** a replacement for your Gulp starter. It is the **operating procedure** so every new page reuses the same proven sequence (including the style of work used on production landings such as **barel.su**).

---

## Who it is for

- **You / your team** building **static** commercial pages with a **Gulp + partials** starter.
- **Implementers** who want AI help **without** full-page dumps, mystery globals, or hand-edited `dist/`.
- **Handoffs** to another developer or stakeholder where a **stable layout baseline** must exist before “fancy” JS.

---

## What problems it solves

| Problem | LS PRO answer |
|--------|----------------|
| Full-page AI output | **One block per response**; **stop after each block** until a human continues. |
| CSS chaos | **BEM only**, styles scoped under the **block root**, **no inline styles**, **no unrelated global changes**. |
| `dist/` hacks | **`src/` only**; **`dist/` only from build**. |
| Responsive spaghetti | **`max-width` media queries** and **one shared breakpoint map** — no stray magic numbers. |
| Unclear “done” | **Stable handoff** (layout frozen) **before** **enhancement phase** (hovers, sliders, modals, light motion). |
| Cursor drift | **`cursor/cursor-system-prompt.txt`** + **one-task template** + **safety rules**. |

---

## Folder structure (actual)

```text
landing-system-pro/
  README.md
  01_start_prompt.txt
  02_rules_core.md
  03_rules_layout.md
  04_rules_cursor.md
  05_git_workflow.md
  06_checklists.md
  07_project_bootstrap.md
  08_handoff_rules.md
  09_enhancement_phase.md
  10_assets_and_content.md
  prompts/
    01_block_implementation.txt
    02_top_area_build.txt
    03_desktop_pass.txt
    04_typography_spacing_pass.txt
    05_catalog_links_pass.txt
    06_media_queries_max_width.txt
    07_mobile_pass.txt
    08_final_polish.txt
    09_stable_handoff.txt
    10_enhancements_phase.txt
  cursor/
    cursor-system-prompt.txt
    cursor-task-template.txt
    cursor-git-template.txt
    cursor-safety-rules.txt
  templates/
    project-kickoff-template.md
    design-analysis-template.md
    block-report-template.md
    final-review-template.md
```

---

## Exact work order (use every project)

| Step | Phase | What to open |
|-----:|--------|----------------|
| 0 | Bootstrap repo from Gulp starter | `07_project_bootstrap.md` |
| 1 | Kickoff + design breakdown | `templates/project-kickoff-template.md`, `templates/design-analysis-template.md` |
| 2 | Lock rules in ChatGPT | `01_start_prompt.txt` + attach `02_rules_core.md`, `03_rules_layout.md` |
| 3 | Top of page | `prompts/02_top_area_build.txt` |
| 4 | Each lower section (repeat) | `prompts/01_block_implementation.txt` |
| 5 | Desktop alignment | `prompts/03_desktop_pass.txt` |
| 6 | Typography + vertical rhythm | `prompts/04_typography_spacing_pass.txt` |
| 7 | Semantics + links + grids | `prompts/05_catalog_links_pass.txt` |
| 8 | Unify breakpoints | `prompts/06_media_queries_max_width.txt` |
| 9 | Mobile | `prompts/07_mobile_pass.txt` |
| 10 | Final polish (no new features) | `prompts/08_final_polish.txt` |
| 11 | Stable handoff doc | `prompts/09_stable_handoff.txt`, `08_handoff_rules.md`, `templates/final-review-template.md` |
| 12 | Enhancements only after sign-off | `09_enhancement_phase.md`, `prompts/10_enhancements_phase.txt` |

Gate between steps using **`06_checklists.md`**.

---

## How ChatGPT and Cursor cooperate

1. **ChatGPT** — sequencing, prompts, and **scoped output** (one block, or one pass: SCSS-only, etc.). **No** unrequested full pages. **Stops** after each deliverable.
2. **Human** — pastes into ChatGPT, approves the next step, may paste AI output into Cursor or ask Cursor to implement from the task text.
3. **Cursor** — edits **`src/`** only, preserves **includes / `@import` order**, runs **`npm run build`** (or the repo’s script), **fixes build in source**, uses **git**: **branch per task or pass**, **commit when green**. **`dist/`** is never hand-edited.

One-line flow: *Prompt → scoped AI output → apply in `src/` → **build** → **commit** → short **block report** → next prompt.*

Cursor behavior is governed by **`04_rules_cursor.md`** and **`cursor/cursor-system-prompt.txt`**.

---

## Lifecycle: kickoff → handoff → enhancements

1. **Kickoff** — design access, desktop width, breakpoint map, assets, CTAs (`07_project_bootstrap.md` + kickoff template).
2. **Structure** — header/hero first, then each section **one block at a time** (`prompts/02`, then `01` on loop).
3. **Passes** — desktop → typography/spacing → semantics/links → breakpoint cleanup → mobile → polish (`prompts/03`–`08`). Each pass is **controlled**; no mixing enhancement JS into layout passes.
4. **Stable handoff** — frozen baseline for programmers: branch/tag, build commands, asset table, known limits (`prompts/09`, `08_handoff_rules.md`).
5. **Enhancement phase** — hovers, transitions, carousels, modals, form UX, light scroll effects **after** stable sign-off (`09_enhancement_phase.md`, `prompts/10`).

---

## First-time use (today)

1. Copy this folder or keep it on disk; point **new client repos** at it when pasting rules/prompts.
2. For **each new page repo**: run **`07_project_bootstrap.md`**, fill **`templates/project-kickoff-template.md`**.
3. Paste **`cursor/cursor-system-prompt.txt`** into Cursor **Project Rules** for that repo.
4. Start ChatGPT with **`01_start_prompt.txt`** and the two core rule files attached.

---

## Maintenance

After a real project, update the **single file that owns that rule** (e.g. breakpoint policy → `03_rules_layout.md`) so the next landing inherits the fix.
