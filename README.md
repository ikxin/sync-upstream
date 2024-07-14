# Sync Upstream Action

[简体中文](./README.zh-CN.md)

This GitHub Action synchronizes a branch of your repository with a branch from an upstream repository.

## Inputs

- `github_token`: GitHub token for authentication.
- `target_repository`: Target repository in the format owner/repo.
- `target_branch`: Branch in the target repository to sync.
- `upstream_repository`: Upstream repository in the format owner/repo.
- `upstream_branch`: Branch in the upstream repository to sync.

## Example Usage

```yaml
name: Sync Upstream

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

jobs:
  sync:
    runs-on: ubuntu-latest

    steps:
      - name: Sync Upstream
        uses: ikxin/sync-upstream@main
        with:
          github_token: ${{ secrets.SYNC_TOKEN }}
          target_repository: "zhcndoc/nuxt"
          target_branch: "upstream"
          upstream_repository: "nuxt/nuxt.com"
          upstream_branch: "main"
```
