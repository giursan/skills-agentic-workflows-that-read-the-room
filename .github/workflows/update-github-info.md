---
name: update-github-info
description: Draft updates for Mona's GitHub Info site using official GitHub sources and open a pull request for review.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before drafting updates.

Read external public guidance with web-fetch and read repository guidance or reference files with GitHub repository API tools instead of terminal, CLI, or sandboxed commands when you need project-specific context.

Use these sources:
- `notes/mona-notes.md`
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/

Use the web-fetch tool to read:
- https://github.blog/latest/
- https://github.blog/changelog/

Review the existing page at `site/content/github-info.md` and update it with concise, practical information that helps developers learn GitHub faster.

Follow these instructions:
- Keep summaries short and useful.
- Prefer updates that help developers learn GitHub faster.
- Mention the source whenever a change comes from the GitHub Blog or the GitHub Changelog.
- Keep the content aligned with Mona's editorial angle: practical GitHub guidance backed by official references.
- Update `site/content/github-info.md` in place.
- Open a pull request for Mona to review before publishing changes.
- Do not write directly to `main`; use `safe-outputs` with `create-pull-request`.
- If no update is needed, say so clearly in the pull request summary and avoid writing direct changes to `main`.

The goal is to draft a high-quality update that Mona can review quickly and merge when appropriate.
