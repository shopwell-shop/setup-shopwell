# Shopwell repository rules

This repository is an independently maintained Shopwell GitHub Action. Every AI
coding agent must read this file before changing files in this repository.

## Hard rules

- Preserve UTF-8 and existing user changes.
- Keep the public action interface Shopwell-branded. Do not reintroduce upstream
  organization references, input names, cache keys, namespaces, or default repositories.
- Runtime code and workflows must not depend on `shopware/*`, `shopwarelabs/*`,
  `@shopware-ag/*`, or their GitHub repositories. A `shopwell-shop/*` Action
  dependency must have a matching entry in the sibling control registry.
- Shopwell-owned npm and Composer dependencies must use a stable version published
  to a real registry. Git URLs, GitHub shorthand/archive/tarball URLs, commits,
  branches, `dev-*`, `file:`, `link:`, and external `workspace:` references are forbidden.
- A package release is complete only after the exact version is queryable through
  its registry API; Git tags, GitHub Releases, and green workflows are insufficient.
- The project uses Apache License 2.0 and root LICENSE contains the standard text.
- Original upstream legal text remains verbatim in root NOTICE.
- Do not create LICENSE.upstream-* files.
- Do not merge or cherry-pick unrelated upstream history; future sync uses patches.
- Do not copy upstream tags or force-push.
- Before commit, push, release, or sync completion, run:
  `../sync-upstream/bin/syncctl audit-license setup-shopwell`
  `../sync-upstream/bin/syncctl audit-upstream-dependencies setup-shopwell`
- A failed audit blocks completion.
- Any LICENSE, NOTICE, action dependency, or upstream legal inventory change must
  update the sibling control repository in the same task.
