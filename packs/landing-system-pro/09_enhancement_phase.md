# Landing System PRO — Enhancement Phase

## Prerequisite

**Stable handoff accepted** — layout, responsive, type, semantics, MQ strategy, and polish are **signed off**. No enhancement work on a moving layout target unless a **layout fix task** is explicitly opened and completed first.

## Principles

- **Trust over spectacle** — commercial landings; motion supports hierarchy, not distraction.
- **Progressive enhancement** — core content readable if JS is slow or off (where realistic for static landings).
- **Stay inside the starter** — same partials, same JS bundling pattern; no shadow architecture.
- **`prefers-reduced-motion`**: disable or simplify non-essential animation.

## Typical buckets

| Bucket | Examples | Watch |
|--------|-----------|--------|
| Hovers / focus | Button, card, link states | Visible keyboard focus |
| Transitions | 150–250ms, simple easing | No layout thrash |
| Sliders | Logos, testimonials | Prev/next, focus, optional swipe |
| Modals | Video, promo, cookies | Focus trap, ESC, return focus |
| Forms | Inline validation hints | Still needs real backend for production |
| Scroll-linked | Section reveals | Debounce; respect reduced motion |

## Suggested order

1. Hover/focus on existing interactives  
2. Small **color/transform/opacity** transitions  
3. **Slider** markup then behavior  
4. **Modals** last (z-index, focus, overlay)

## Guardrails

- **No new global CSS** — scope under block BEM or documented utility layer if the starter has one.
- **Debounce** scroll/resize; clean up listeners if the starter’s pattern requires it.
- **No heavy libraries** for trivial effects — native APIs first.

## Prompting + Cursor

- ChatGPT: **`prompts/10_enhancements_phase.txt`** — **one enhancement type per message**.
- Cursor: **one `task/` branch per enhancement** when possible; build + commit per task.

## Done

- No new **console errors**; quick **accessibility** smoke; behavior noted in block report or client README section.
