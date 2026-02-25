# AGENTS.md

Guidance for AI agents working in this repository.

## Repository purpose

- This repo is a Mintlify documentation project for Elty Davinci.
- Primary configuration lives in `docs.json`.
- Most product documentation lives in `platform/**` and is written in Italian.

## First-step workflow

1. Read `docs.json` to understand current navigation and page paths.
2. Read `.cursor/rules.md` and follow its writing/component rules.
3. Match the language of the page you edit:
   - `platform/**`: Italian
   - Starter/template pages (for example `quickstart.mdx`): English

## Package manager rule (must follow)

Before running any package manager command, check which package manager the repo uses.

Recommended check order:

1. `pnpm-lock.yaml` -> use `pnpm`
2. `yarn.lock` -> use `yarn`
3. `package-lock.json` -> use `npm`

If no lockfile is present, do not assume install steps are required. For local docs preview in this repo, use Mint CLI commands only when needed.

## Required page conventions

### For `platform/**` pages

- Frontmatter must include both:
  - `title`
  - `sidebarTitle`
- Keep section hierarchy clear and consistent.
- Preserve the existing instructional tone and terminology used on nearby pages.

Example:

```yaml
---
title: "Referti"
sidebarTitle: "Referti"
---
```

### For non-`platform/**` pages

- Use frontmatter with:
  - `title`
  - `description`

## Navigation rules

- When adding a new page, also update `docs.json` navigation under the correct group/tab.
- Use extensionless page paths in `docs.json` (for example `platform/connect/referti`).
- Keep nav ordering consistent with related pages.

## Media and links

- Use root-relative image paths from `images/`, for example `/images/platform/profilo/image.png`.
- Prefer stable filenames without spaces for new assets.
- Add descriptive alt text when practical.
- Use Mintlify callouts (`<Tip>`, `<Note>`, `<Warning>`) instead of raw Notion `<aside>` blocks.

## Editing guardrails

- Make focused changes only; avoid broad rewrites unless requested.
- Keep existing page structure unless there is a clear quality issue to fix.
- Do not rename/move files unless required by the task.

## Validation checklist

Run relevant checks for touched files:

1. `python -m json.tool docs.json >/dev/null` after editing `docs.json`.
2. `mint broken-links` when you add/modify links (if Mint CLI is available).
3. Preview with `mint dev` when layout or component rendering may be affected.

If a command cannot run because of environment limitations, report the limitation clearly.

## Cursor Cloud specific instructions

- Prefer minimal, high-signal validation commands over full-repo heavy checks.
- For doc-only changes, validate the touched files and navigation integrity rather than running unrelated test suites.
- In final updates, explicitly list:
  - files changed
  - checks run
  - any unresolved risks (for example unverified UI rendering if preview was not run)
