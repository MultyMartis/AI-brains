# AI-brains

**AI-brains** is the canonical, reusable AI knowledge repository for this workspace. It holds prompts, packaged workflows, and portable instruction text that agents and humans can reuse across projects.

## Layout

| Path | Purpose |
|------|--------|
| `prompts/` | Reusable prompt libraries (short, composable task prompts). |
| `packs/` | Larger workflow systems and packaged methodologies (full “brains” for a domain or delivery pipeline). |
| `system/` | Reusable global instructions and operating rules (portable system-level text, not project-specific). |

## What this repo is not

- **Project and site code are intentionally excluded.** Application source, client trees, build outputs, and IDE-specific junk do not belong here.
- **Secrets and environment-specific config** do not belong here. Do not commit API keys, `.env` files, or credentials.

## Source of this assembly

Content was **copied** (not moved) from earlier scattered locations under `D:\AI`. The original folders (for example `D:\AI\AI` and `D:\AI\landing-system-pro`) still exist until a later reorganization pass; this tree is the single curated place to grow reusable “brains” going forward.

## Contributing

Add new reusable prompts under `prompts/` (by topic or library name). Add or version full methodologies under `packs/<name>/`. Keep `system/` for cross-cutting rules that apply regardless of which pack or project is in use.
