# Landing System PRO — Git Workflow

Use this in **each client page repo**. The **LS PRO pack** itself may also use git locally — **no remote required** for either.

## Branch naming

| Pattern | Use |
|--------|-----|
| `main` / `master` | Integration / release line |
| `task/<short-slug>` | One block, one bugfix, or one small enhancement |
| `pass/<short-slug>` | Repo-wide single pass (e.g. `pass/typography`, `pass/unify-mq`) |
| `fix/<short-slug>` | Production fix |
| `chore/<short-slug>` | Tooling, deps, agreed-only formatting |

Examples: `task/hero-html`, `pass/mobile-all-blocks`, `fix/header-overflow`.

## Commits

**Prefix + scope + imperative summary** (Conventional-style, short):

- `feat(hero): desktop grid and CTAs`
- `style(catalog): typography and spacing pass`
- `fix(nav): z-index and mobile toggle`
- `chore(build): refresh lockfile for Node 20`

Optional **body**: why, how to test, screenshots note.

## When to commit

- **End of each Cursor task** when **build passes**.
- **Before** starting a new pass if the previous work is complete — avoid mixing unrelated changes.
- **Avoid** committing broken builds unless the team explicitly uses WIP branches — prefer **small, green** commits.

## Tags (optional)

- `v-handoff-1.0` — layout stable; enhancements not included.
- `v-enhance-1.1` — named enhancement batch merged.

## Merge / remotes

- If **no remote**: branching + commits still give local checkpoints and diffs.
- If **remote exists**: pull/rebase from `main` before long tasks; resolve conflicts in **`src/`**, then **rebuild** before push.

## `dist/` policy

- If `dist/` is **tracked**: commit it **only** as the **output of** a successful build from matching **`src/`**. **Never** patch `dist/` alone.

## LS PRO pack vs client repo

- **Client repo**: full workflow, all branches above.
- **This pack** (`landing-system-pro/`): optional git for versioning the **docs/prompts** themselves — same discipline, smaller scope.
