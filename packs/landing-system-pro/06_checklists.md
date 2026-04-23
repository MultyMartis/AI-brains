# Landing System PRO — Checklists

Use as **gates**: do not start the next **prompt file** until the current phase is checked.

## New project kickoff

- [ ] Design source locked (Figma / PDF / image set)
- [ ] Gulp starter instantiated; `npm install` OK
- [ ] **Build** (`npm run build` or project script) succeeds; `dist/` reflects `src/`
- [ ] ChatGPT session seeded with `01_start_prompt.txt` + **`02_rules_core.md`** + **`03_rules_layout.md`**
- [ ] Cursor: **`cursor/cursor-system-prompt.txt`** (+ safety rules) for the **client repo**
- [ ] `templates/project-kickoff-template.md` started; **`templates/design-analysis-template.md`** has section list + BEM roots

## Per block (HTML structure — `prompts/01` or `02`)

- [ ] Single **BEM root** per section
- [ ] Semantic tags match content; heading levels consistent with prior blocks
- [ ] **No inline styles**
- [ ] Images: **`alt`**; decorative images: empty `alt` + note in block report
- [ ] Links: real `href` or documented `#anchor` / placeholder policy from kickoff
- [ ] ChatGPT **stopped** after the block; human/Cursor applied + **build** + **commit** before next block

## Desktop pass (`prompts/03`)

- [ ] Matches design at **agreed desktop width**
- [ ] Columns, gutters, alignment; **no new breakpoints** invented here
- [ ] **No `overflow-x`** at primary desktop width

## Typography + spacing (`prompts/04`)

- [ ] Type scale / weights / line-heights match design for **target blocks only**
- [ ] Vertical spacing uses **tokens/scale** — no random one-off margins without reason
- [ ] **No** column/grid redesign “while fixing fonts”

## Semantic + links (`prompts/05`)

- [ ] Landmarks: `header` / `nav` / `main` / `footer` sensible
- [ ] No “click here”; no raw URLs as link text
- [ ] **`<a>`** for navigation; **`<button type="button">`** for JS-only actions
- [ ] Repeated cards/lists use consistent, accessible pattern

## Media queries (`prompts/06`)

- [ ] All `@media` use **shared breakpoint map** — no orphan pixel values
- [ ] No duplicate conflicting rules for the same selector/breakpoint pair

## Mobile pass (`prompts/07`)

- [ ] Tested at **kickoff’s** tablet + phone widths
- [ ] Tap targets **≥ ~44px** effective for primary actions
- [ ] Sticky/fixed chrome does not hide CTAs
- [ ] **No horizontal scroll** at test widths

## Final polish (`prompts/08`)

- [ ] Micro-alignment only — **no new components**, **no enhancement JS**
- [ ] Cross-browser smoke if required by kickoff
- [ ] **Build clean**; open `dist/` (or serve) — **no console errors** on static load

## Stable handoff (`prompts/09`)

- [ ] No mixed-in enhancement experiments
- [ ] Branch or tag recorded; **install + build** commands written for the next developer
- [ ] Placeholder assets listed with **replacement specs**

## Enhancement phase (`prompts/10`)

- [ ] **Signed off** stable handoff first
- [ ] Each enhancement: isolated **BEM + JS**; **`prefers-reduced-motion`** where relevant
- [ ] Sliders/modals: keyboard + **focus** behavior checked
