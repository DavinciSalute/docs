---
name: sync-docs-from-github
description: Synchronize Mintlify documentation with recent code changes from GitHub repository qa branch. Use when the user wants to update docs based on recent commits, sync documentation, or mentions updating docs from GitHub, qa branch, or DavinciSalute/davinci repository.
---

# GitHub → Mintlify Docs Sync Agent

This skill helps synchronize the Mintlify documentation with recent code changes from the `DavinciSalute/davinci` repository's `qa` branch.

## Quick Start

When invoked, follow this workflow:

1. Fetch recent commits from qa branch
2. Identify documentation-relevant changes
3. Update or create corresponding documentation pages
4. Create a pull request with the changes

## Step 1: Fetch Recent Commits

Use the GitHub MCP `list_commits` tool:

```
CallMcpTool:
  server: "user-GitHub"
  toolName: "list_commits"
  arguments:
    owner: "DavinciSalute"
    repo: "davinci"
    sha: "qa"
    perPage: 10
```

**Output**: List of recent commits with SHA, message, author, and date.

## Step 2: Analyze Commits for Documentation Relevance

For each commit, determine if it's documentation-relevant:

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

**Branch naming:**
```
docs/sync-from-davinci-YYYY-MM-DD
```

Example: `docs/sync-from-davinci-2026-02-02`

**PR Title:**
```
Docs: sync updates from DavinciSalute/davinci (qa branch, <date>)
```

**PR Description Template:**
```markdown
## Summary

- Updated [feature/page] based on commit [SHA]
- Added documentation for [new feature] (commit [SHA])
- Revised [section] to reflect [change] (commit [SHA])

## Motivation

Syncing documentation with recent changes on qa branch:
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
1. Create branch: `git checkout -b docs/sync-from-davinci-YYYY-MM-DD`
2. Stage changes: `git add .`
3. Commit: `git commit -m "docs: sync from qa branch (YYYY-MM-DD)"`
4. Push: `git push -u origin HEAD`

Then use `gh pr create` with the template above.

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
- head: "docs/sync-from-davinci-YYYY-MM-DD"

## Best Practices

1. **Never invent information**: Only document what's explicitly in the commits/diffs
2. **Reference commit SHAs**: Always link changes back to specific commits
3. **Maintain Mintlify style**: Follow existing documentation patterns
4. **Keep language consistent**: Use Italian as per existing docs
5. **Flag uncertainties**: If unsure about a change's impact, note it clearly in PR

## Troubleshooting

**No documentation-relevant changes found:**
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
User: "Update docs from recent qa changes"

1. Fetch last 10 commits from DavinciSalute/davinci qa branch
2. Identify 3 documentation-relevant commits:
   - abc123: New agenda time slots feature
   - def456: Updated patient search filters
   - ghi789: Added prescription renewal flow
   
3. Map to docs:
   - abc123 → Update platform/funzionalita/agenda.md
   - def456 → Update platform/pazienti/ricerca-paziente.md
   - ghi789 → Update platform/pazienti/ricette.md
   
4. Apply changes to the 3 files
5. Create branch: docs/sync-from-davinci-2026-02-02
6. Commit and push changes
7. Create PR with detailed description referencing all 3 commits
```
