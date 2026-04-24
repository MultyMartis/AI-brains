# AI-brains

**AI-brains** is the canonical, reusable **AI knowledge base** for **MCA AI.Pack** and **MetaCODE**. It holds global operating rules, workflow standards, prompt libraries, packaged methodologies, and documentation that agents and humans reuse across projects—without mixing in application source code.

## What this repository contains

- **Global system rules** — precedence, SAFE UNKNOWN, wiring standards, Git safety (`system/`).
- **Prompt packs** — short, composable task prompts (`prompts/`).
- **Workflow standards** — trackers, templates, lifecycle and registry standards (`system/`, `logs/`).
- **Project control docs** — project registry, lifecycle log, project-control rules (`system/project-registry.md`, `logs/lifecycle-log.md`, related standards).
- **Main Brain v2 architecture** — layers, operating cycle, WebGPT memory integration ([`system/main-brain-v2-architecture.md`](system/main-brain-v2-architecture.md)).

## Key entry points

| Document | Purpose |
|----------|---------|
| [`system/main-brain-v2-architecture.md`](system/main-brain-v2-architecture.md) | Main Brain v2 layers, image, operating cycle |
| [`system/ai-brains-system-index.md`](system/ai-brains-system-index.md) | System file index for agents |
| [`system/metacode-mission.md`](system/metacode-mission.md) | MetaCODE mission |
| [`system/webgpt-memory-module.md`](system/webgpt-memory-module.md) | WebGPT chat migration and memory |
| [`logs/lifecycle-log.md`](logs/lifecycle-log.md) | AI lifecycle change log |

## Layout

| Path | Purpose |
|------|--------|
| `prompts/` | Reusable prompt libraries (short, composable task prompts). |
| `packs/` | Larger workflow systems and packaged methodologies (full “brains” for a domain or delivery pipeline). |
| `system/` | Reusable global instructions and operating rules (portable system-level text, not project-specific). |
| `assets/` | Shared assets for documentation (for example architecture diagrams). |
| `logs/` | Lifecycle and other controlled logs. |

## What this repo is not

- **Project and site code are intentionally excluded.** Application source, client trees, build outputs, and IDE-specific junk do not belong here.
- **Secrets and environment-specific config** do not belong here. Do not commit API keys, `.env` files, or credentials.

## Source of this assembly

Content was **copied** (not moved) from earlier scattered locations under `D:\AI`. The original folders (for example `D:\AI\AI` and `D:\AI\landing-system-pro`) still exist until a later reorganization pass; this tree is the single curated place to grow reusable “brains” going forward.

## Contributing

Add new reusable prompts under `prompts/` (by topic or library name). Add or version full methodologies under `packs/<name>/`. Keep `system/` for cross-cutting rules that apply regardless of which pack or project is in use. Register significant system changes in [`logs/lifecycle-log.md`](logs/lifecycle-log.md) per project standards.
