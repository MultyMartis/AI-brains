# Landing System PRO — Project Bootstrap

Repeatable steps for **each new** landing or standalone commercial page repo (Gulp + HTML + SCSS + JS).

## 1. Starter

- Use your **canonical Gulp starter** (same one LS PRO was tuned for).
- Copy or duplicate; rename root to `client-slug-page` (or your convention).

## 2. Git (client repo)

```text
git init
git add .
git commit -m "chore: initial import from gulp starter"
```

Optional: create `main` as default branch name. **Remote optional** — LS PRO works with **local git only**.

## 3. First build

- `npm install` (or documented install).
- Run **`npm run build`** (or `gulp build` — whatever the starter README says).
- Fix starter issues **before** block implementation begins.

## 4. Project docs (human)

From **`templates/project-kickoff-template.md`** fill: client, URLs, design links, **desktop comp width**, **max-width breakpoint map**, fonts, forms/analytics if any.

From **`templates/design-analysis-template.md`**: ordered section list, **BEM block name per section**, sticky header behavior, hero metrics.

## 5. Wire LS PRO into the workflow

- **ChatGPT**: attach `02_rules_core.md`, `03_rules_layout.md`, and the **current** file from **`prompts/`**.
- **Cursor** (client repo): add **`cursor/cursor-system-prompt.txt`** to Project Rules; use **`cursor/cursor-task-template.txt`** per task.
- **Optional**: copy `prompts/` snippets into `client-repo/docs/ls-pro/` for offline reference — note **date/version** in a one-line README if you do.

## 6. Client `src/` hygiene

- **`src/`** — all authoring.
- **`dist/`** — generated; never “quick fixed” by hand.
- Optional **`docs/`** in client repo for **`templates/block-report-template.md`** exports per task.

## 7. Implementation order

1. **`prompts/02_top_area_build.txt`** — header + hero (or combined top).
2. **`prompts/01_block_implementation.txt`** — repeat for each subsequent block.
3. Passes **`03` → `04` → `05` → `06` → `07` → `08` → `09`** on the **whole page** (or scoped block lists if agreed).
4. **`prompts/10_enhancements_phase.txt`** — **only after** stable handoff sign-off.

## 8. Definition of done

- **Green build**; design match at agreed viewports; **handoff doc** + **final review** completed; enhancement work clearly separated if deferred.
