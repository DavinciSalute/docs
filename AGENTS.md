# AGENTS.md

## Repository purpose
- This repository hosts Mintlify documentation for Elty Davinci.
- Main content lives in `.mdx` files under folders like `platform/`, `essentials/`, `api-reference/`, and `quickstart.mdx`.
- Site navigation, theme, branding, and top-level structure are configured in `docs.json`.

## Content editing guidelines
- Keep frontmatter (`title`, `description`) present and accurate on every docs page.
- Preserve the existing language and tone of each page (many pages are in Italian).
- When adding, removing, or renaming pages, update `docs.json` navigation entries in the same change.
- Use existing image path conventions (for example `/images/...`) and keep asset references valid.

## Package manager and tooling rule
- Before running any package-manager command, check which package manager is used in the repository.
- Detect package manager by checking lockfiles/configs first (`pnpm-lock.yaml`, `yarn.lock`, `package-lock.json`, `pyproject.toml`, etc.).
- If no repo-specific package manager is defined, default to the command style already documented in this repo (`npm` for Mintlify CLI usage).

## Validation checklist for docs changes
- Confirm all edited/added pages are referenced correctly in `docs.json` (when applicable).
- Validate links and page references before finishing work.
- If Mintlify CLI is available, run `mint broken-links` from repo root.
- Avoid long-running local preview commands in cloud agents unless explicitly requested (for example `mint dev`).

## Cursor Cloud specific instructions
- Prefer Cursor tools (`ReadFile`, `Glob`, `rg`, `ApplyPatch`) over shell file-read/edit commands.
- Keep edits focused; avoid unrelated formatting churn.
- For UI/manual verification requests, use the computer-use workflow and attach a short walkthrough artifact.
- Commit and push changes on the active feature branch after completing updates.
