# Landing System PRO — Layout & Responsive Rules

## Desktop first, then passes

- Lock **desktop** composition per block before dedicated **typography/spacing** passes (do not redesign the grid during the type pass).
- Use a **spacing scale** consistent with the design (e.g. 4/8/12/16/24/32/48/64); prefer **project variables** if the starter defines them.

## Media queries: max-width only

- Use **`@media (max-width: …)`** for layout changes. Typical cascade (tune to kickoff): **1199 → 991 → 767 → 575** px or your agreed map.
- **Single source of truth**: one SCSS partial (e.g. `_breakpoints.scss`) or map — **no duplicate breakpoint literals** in every block file.
- Adjust columns/gaps **per breakpoint token**, not one-off random widths, unless the design demands it — then **document** in the block report.

## Containers

- Honor the starter’s **max content width** and **horizontal padding**.
- **Full-bleed background + inner content width**: background on the outer BEM block; **inner** wrapper constrains text and grids.

## Grid and alignment

- **Flexbox/Grid** per design — no tables for layout.
- **Vertical rhythm**: align related headings, body, and CTAs to the same spacing system.

## Imagery

- **Hero**: often full-width; set **min-height** or **aspect-ratio** to match the comp.
- **Logos/icons**: fixed box + **`object-fit: contain`** where appropriate.
- **Background photos**: watch **contrast**; use overlay variables if the design uses them.

## Overflow

- After mobile-related changes, verify **no accidental `overflow-x`** (fixed widths, large negative margins, unbreakable strings).

## Z-index

- Central small scale: e.g. header, dropdown, overlay, modal — define once, reuse tokens.

## Do not

- Do not “fix” one section by editing **global layout primitives** (site wrapper, base grid) — fix the **section BEM root** or the kickoff if the starter is wrong.
- Do not use **fixed** layout for large sections without a spec (sticky header is OK if required).
