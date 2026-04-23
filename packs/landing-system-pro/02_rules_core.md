# Landing System PRO — Core Rules

## Scope

Applies to **landing pages** and **standalone commercial pages**: **HTML + SCSS + JS**, **Gulp**, **BEM**, **pixel-accurate** blocks, **max-width** responsive strategy. Canonical code lives in the **project repo**; ChatGPT outputs **snippets** to paste or tasks for Cursor.

## One block at a time

- A **block** = one coherent UI section (header, hero, catalog grid, testimonials, footer, etc.).
- **One block per generation step** unless the human explicitly asks for more in one message.
- **Stop after each block** — no chaining the rest of the page without approval.

## Controlled changes only

- Each pass has **one job** (e.g. desktop layout only, or typography only). Do not “fix” other passes in the same output unless blocking breakage — then list what you had to touch and why.

## Source of truth

- **Edit only `src/`** (partials, SCSS, JS as the starter defines).
- **`dist/` is build output only** — never hand-edit to “save time.”
- Build fails → fix **paths, includes, SCSS, JS** in **`src/`**, then rebuild.

## CSS

- **BEM only** for styling hooks: `.block`, `.block__element`, `.block--modifier`.
- **No inline styles** on markup.
- Avoid **new global element rules** (e.g. `section { margin: ... }`) that leak outside the block; scope under the **block root**.
- **`!important`**: avoid; use only with a one-line comment if the starter forces an exception.

## Assets

- **Placeholders**: explicit filenames and target dimensions in the block report / handoff.
- **`object-fit`**: `cover` when controlled crop is OK (many heroes/cards); `contain` when the full image must show (logos). Pair with **`aspect-ratio`** or explicit box where layout depends on it.

## JavaScript

- **Feature-scoped** modules; no frameworks unless the project already uses them.
- **Layout passes** should not add enhancement behavior (sliders, modals, scroll FX) — see `09_enhancement_phase.md`.

## Quality bar

- **Semantic HTML** (`header`, `nav`, `main`, `section`, `footer`); **one logical `h1`** per page unless the kickoff doc allows otherwise.
- **a11y basics**: meaningful links, `alt` on informative images, visible **focus** for interactive controls.
- **Performance**: lazy-load non-critical images when the starter supports it.

## Handoff order

- **Stable handoff** = layout + responsive + type + links + MQ strategy accepted — **before** programmer transfer or heavy **enhancement** work. Details: `08_handoff_rules.md`, `09_enhancement_phase.md`.
