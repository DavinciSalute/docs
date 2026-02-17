---
name: sync-docs-from-github
description: Synchronize Mintlify documentation with recent code changes from GitHub repository master branch. Use when the user wants to update docs based on recent commits, sync documentation, or mentions updating docs from GitHub, master branch, or DavinciSalute/davinci repository.
---

# GitHub → Mintlify Docs Sync Agent

This skill helps synchronize the Mintlify documentation with recent code changes from the `DavinciSalute/davinci` repository's `master` branch.

## Quick Start

1. Read `latest_commit.md` to get the last analyzed commit SHA (so we don’t re-analyze the same commits).
2. `list_commits(DavinciSalute, davinci, master, perPage: 20)` → keep only commits **newer** than that SHA (newest-first; stop when you reach it).
3. Analyze only those new commits; update/create doc pages.
4. **Update `latest_commit.md`** with the newest commit analyzed this run. No new commits → leave unchanged.
5. **Use the same umbrella branch** every time: checkout `docs/sync-from-davinci`, apply changes, commit, push. Open the PR (or update the existing one). One branch for all sync runs; a reviewer controls when to merge (see Step 5).

## Step 1: latest_commit.md + fetch only new commits

### 1a. Read latest_commit.md

Read `.cursor/skills/sync-docs-from-github/latest_commit.md`.

- If it exists and contains a **SHA** (e.g. in a line like `**SHA:** \`abc123...\``), → last analyzed; only analyze **newer** commits.
- If the file is missing or has no SHA, treat as first run: all commits you fetch will be considered “new” and analyzed.

### 1b. Fetch commits and filter to “new” ones only

Use the GitHub MCP `list_commits` tool:

```
CallMcpTool:
  server: "user-GitHub"
  toolName: "list_commits"
  arguments:
    owner: "DavinciSalute"
    repo: "davinci"
    sha: "master"
    perPage: 20
```

The API returns commits **newest first**. From this list:

- **If you have a last-analyzed SHA from latest_commit.md:** walk from the top and collect commits until you **reach** that SHA. The commits you collected **before** reaching it are the **new** ones to analyze. Do **not** analyze the last-analyzed commit again; only analyze the newer ones.
- **If you have no last-analyzed SHA:** treat the whole fetched list as new and analyze all (or the first N you need).

If the last-analyzed SHA does not appear in the first page, fetch more pages (`page: 2`, etc.) until you find it, then “new” commits are all those from the start of the list down to (but not including) that SHA. If master has moved and that SHA is no longer in the history, treat the whole first page as new.

**Output to use:** the list of **new** commits only (SHA, message, author, date).

### 1c. Update latest_commit.md at the end of the run

After you finish analyzing (and optionally updating docs), **update** `.cursor/skills/sync-docs-from-github/latest_commit.md` with the **last commit that was analyzed in this run** — i.e. the **newest** among the commits you actually considered (first in the “new” list). That way the next run will start after this commit and again only analyze newer commits.

**Format for latest_commit.md:**

```markdown
# Ultimo commit analizzato (DavinciSalute/davinci, master)

- **SHA:** `{full SHA}`
- **Data:** {date in ISO or YYYY-MM-DD HH:MM:SS UTC}
- **Autore:** {author name or login}
- **Messaggio:** {full commit message, first line or summary}
- **URL:** https://github.com/DavinciSalute/davinci/commit/{SHA}
```

- **If you analyzed at least one commit:** set the file to the **newest** of those (the first in the “new” list).
- **If there were no new commits:** leave the file unchanged (or set it to the current HEAD of master if you prefer to advance the pointer anyway).
- **If it was a first run:** set the file to the newest commit you analyzed.

This keeps the “last analyzed” pointer correct and avoids double-analyzing the same commits on the next run.

## Step 2: Analyze for doc relevance

For each commit, determine if it's doc-relevant:

### Relevant Changes Include:
- New features or endpoints
- UI/UX changes visible to end users
- Configuration changes affecting user workflow
- New settings or options
- Deprecated functionality
- Bug fixes that change expected behavior

### Not Relevant:
- Internal refactoring without user-facing impact
- Dependency updates
- Test changes
- CI/CD modifications

### Build Documentation Map

Create an internal map (do not include in PR description):

```
Commit SHA | Changed Files | Change Description | Affected Doc Pages
-----------|---------------|-------------------|-------------------
abc123     | src/agenda.ts | Added time slots  | platform/funzionalita/agenda.md
def456     | api/ricette   | New API endpoint  | NEW: platform/pazienti/ricette-api.md
```

## Step 3: Map to Mintlify Documentation Structure

Reference the current documentation structure in `docs.json`:

**Current Navigation Groups:**
- Pazienti (platform/pazienti/*)
- Funzionalità (platform/funzionalita/*)
- Configurazione (platform/configurazione/*)
- Supporto (platform/supporto/*)
- Info extra (platform/piani-tariffari, platform/qa)

**Actions:**
- **Update existing page**: Modify content in relevant .md file
- **Create new page**: Add new .md file in appropriate directory
- **Update navigation**: Modify docs.json if adding new pages

## Step 4: Apply Documentation Changes

Use standard file editing tools to:

1. Update existing `.md` files with new information
2. Create new `.md` files following Mintlify format
3. Update `docs.json` navigation if adding new pages

**Mintlify File Format:**
```markdown
---
title: "Page Title"
description: "Brief description"
---

# Main Heading

Content following Mintlify best practices...
```

## Step 5: Create Pull Request

### Umbrella branch (reuse the same branch every run)

**Use a single branch for all sync runs.** one recurring branch and one PR (updated each run) is preferred.

1. **Branch name (fixed):** `docs/sync-from-davinci`
2. **Each run:** Check out this branch (create it if it doesn’t exist). If it already exists remotely, pull latest first so you’re up to date, then apply doc changes, commit, and push.
3. **PR:** Open a PR from `docs/sync-from-davinci` if there isn’t one yet; otherwise the existing PR is updated with the new commits. The same reviewer can merge when ready.

**Branch naming:**
```
docs/sync-from-davinci
```
(One branch for all runs) If the branch was merged and deleted on the remote, create it again from current `master`/`main` and push; then open a new PR.

**PR Title:** (use when creating the PR; include date of this run’s sync)
```
Docs: sync updates from DavinciSalute/davinci (master branch, <date>)
```

**PR Description Template:**
```markdown
## Summary

- Updated [feature/page] based on commit [SHA]
- Added documentation for [new feature] (commit [SHA])
- Revised [section] to reflect [change] (commit [SHA])

## Motivation

Syncing documentation with recent changes on master branch:
- Commit range: [oldest SHA]...[newest SHA]
- Date range: [start date] to [end date]

## Files Modified/Created

- Updated: platform/funzionalita/agenda.md
- Created: platform/pazienti/new-feature.md
- Updated: docs.json (added navigation entry)

## Source Commits

- [abc123] - Added time slot selection to agenda
- [def456] - Implemented prescription request API
```

Use Git commands to:
1. Checkout the umbrella branch (create if first time): `git fetch origin` then `git checkout docs/sync-from-davinci` or, if it doesn’t exist, `git checkout -b docs/sync-from-davinci`. If the branch already exists on origin, `git pull origin docs/sync-from-davinci` to update.
2. Stage changes: `git add .`
3. Commit: `git commit -m "docs: sync from master branch (YYYY-MM-DD)"` (use current date).
4. Push: `git push -u origin docs/sync-from-davinci`

Then open a PR with the template above if there isn’t one yet; otherwise the push updates the existing PR.

## GitHub MCP Tools Reference

**List commits:**
```
list_commits(owner, repo, sha, page, perPage)
```

**Get file contents:**
```
get_file_contents(owner, repo, path, branch)
```

**Create pull request:**
```
create_pull_request(owner, repo, title, body, head, base)
```

For the docs repository:
- owner: Check git remote (likely your username or organization)
- repo: "docs"
- base: "master" (or main branch)
- head: "docs/sync-from-davinci"

## Inspecting a single commit (files + diff) — GitHub CLI

When you need to see **which files changed** and the **patch** for a single commit in a GitHub repo, and no MCP tool exposes that (e.g. commit is not part of a PR), use **GitHub CLI** (`gh`). This applies to any workflow, not only this skill.

- **Commands** — replace `OWNER`, `REPO`, `SHA`, `BASE_SHA`, `HEAD_SHA` with the real values; use `gh` or the full path as above:
  - List files changed in a commit:
    ```bash
    gh api repos/OWNER/REPO/commits/SHA --jq '.files[] | {filename, status, additions, deletions}'
    ```
  - Get full patch per file:
    ```bash
    gh api repos/OWNER/REPO/commits/SHA --jq '.files[] | {filename, patch}'
    ```
  - Compare two commits (range):
    ```bash
    gh api repos/OWNER/REPO/compare/BASE_SHA...HEAD_SHA --jq '.files[] | {filename, patch}'
    ```
- Use these whenever commit-level diff is needed and the only way to get it is via the GitHub API (e.g. via `gh`).


## Best Practices

1. **Never invent information**: Only document what's explicitly in the commits/diffs
2. **Reference commit SHAs**: Always link changes back to specific commits
3. **Maintain Mintlify style**: Follow existing documentation patterns
4. **Keep language consistent**: Use Italian as per existing docs
5. **Flag uncertainties**: If unsure about a change's impact, note it clearly in PR

## Troubleshooting

**No doc-relevant changes found:**
- Report this clearly to the user
- Offer to check an earlier date range

**Unable to determine affected docs page:**
- Create entry under "Supporto" or appropriate catch-all section
- Note in PR that categorization needs review

**Conflicts with existing documentation:**
- Preserve existing content structure
- Add new information without removing context
- Note conflicts in PR description for manual review

## Example Workflow

```
User: "Update docs from recent master changes"

1. Read .cursor/skills/sync-docs-from-github/latest_commit.md → last analyzed SHA: xyz789
2. Fetch last 20 commits from DavinciSalute/davinci master; filter to commits newer than xyz789 → 3 new commits (abc123, def456, ghi789)
3. Analyze only those 3 for doc relevance:
   - abc123: New agenda time slots feature
   - def456: Updated patient search filters
   - ghi789: Added prescription renewal flow
   
4. Map to docs:
   - abc123 → Update platform/funzionalita/agenda.md
   - def456 → Update platform/pazienti/ricerca-paziente.md
   - ghi789 → Update platform/pazienti/ricette.md
   
5. Apply changes to the 3 files
6. Update latest_commit.md with abc123 (newest commit analyzed this run)
7. Checkout umbrella branch docs/sync-from-davinci (pull if exists), apply changes, commit, push
8. Open PR (or existing PR is updated) with detailed description referencing all 3 commits
```
