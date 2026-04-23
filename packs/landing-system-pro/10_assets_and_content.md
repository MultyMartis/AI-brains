# Landing System PRO — Assets & Content

## Raster / vector

- **Photos**: WebP when the pipeline supports it; otherwise follow starter defaults.
- **Logos / icons**: **SVG** first; PNG when the asset is not practical as SVG.

## Naming and sizing

- Name by **role**: `hero-bg.webp`, `product-card-fallback.jpg`, `logo-client.svg` — not camera defaults.
- Provide **@2x** or SVG for sharp UI; match **design box** aspect to reduce reflow.

## `object-fit`

| Case | Choice |
|------|--------|
| Hero / uniform cards, crop OK | `cover` + defined box / `aspect-ratio` |
| Logos, partner marks, “must see whole image” | `contain` |
| Decorative fills | document if `cover` crops branding |

## Placeholders

- Folder example: `src/assets/img/placeholders/` with names like `hero-1920x800.jpg`.
- Handoff **must** list: path, **final** intended dimensions, rights status.

## Copy

- Prefer **real copy** before final polish — lorem breaks line breaks and CTA rows.
- If temporary copy ships: mark in **limitations**, not as silent final content.

## Video / third-party

- **iframes**: lazy where possible; fixed aspect container.
- **`<video>`**: `poster`; **no** autoplay with sound.

## Fonts

- List **weights in use**; avoid duplicate `@font-face` blocks scattered in partials — follow starter’s font entry.

## Legal / tracking

- Cookie / consent / analytics snippets: **explicit tasks**; often fit **enhancement phase** if not MVP.

## Pre-ship

- [ ] Images compressed per project rule
- [ ] Meaningful **`alt`**
- [ ] No multi‑MB accidental binaries in git
