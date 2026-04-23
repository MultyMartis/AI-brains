# Landing System PRO — Handoff Rules

## A. Stable handoff (layout-complete)

**Purpose:** Give a developer or stakeholder a **known-good baseline**: structure, responsive behavior, typography, links, unified breakpoints — **without** optional motion/widgets unless they were **explicit MVP**.

**Include**

- Git **branch name** and/or **tag** (e.g. `handoff/stable-1`, `v-handoff-1.0`)
- **Node** version (if non-default) and commands: `npm install`, **build**, optional **watch**
- **Source map**: main HTML partial(s), SCSS entry/partials for this page, JS entry if used
- **Breakpoint map + max content width** (final numbers)
- **Asset table**: path, type, **final vs placeholder**, dimensions/license notes
- **Known limitations**: TODOs that are **intentional** until post-handoff
- Confirmation: **`dist/`** was produced by **build**, not manual edits

**Exclude**

- Half-finished **enhancement** JS (sliders, modals, scroll effects) not approved for MVP
- Silent `href="#"` / lorem left as if final — either fix or list explicitly under limitations

## B. Enhancement delivery (post-stable)

**Purpose:** Small, **revert-friendly** increments: hovers, transitions, carousels, modals, client-side form polish.

Each batch should:

- Reference the **stable** tag/branch in commit message or doc
- Touch **minimal files**; keep BEM boundaries clean
- Have its own **test notes** (keyboard, focus, reduced motion)

## Documentation

- Sign-off: **`templates/final-review-template.md`**
- AI-generated handoff body: **`prompts/09_stable_handoff.txt`**

## Assets for the next person

- Separate **licensed finals** vs **placeholders**
- For each placeholder: **export size**, **format**, **subject** so art can drop in without re-layout

## Code state

- **BEM roots stable** — no pending mass-renames
- **Breakpoints** only via shared map/variables

## Communication

- After each Cursor task: short **`templates/block-report-template.md`** — faster than one monolithic dump at the end.
