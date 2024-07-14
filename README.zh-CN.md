# 同步上游操作

[English](./README.md)

这个 GitHub 操作将你的仓库分支与上游仓库的分支同步。

## 输入

- `github_token`: 用于认证的 GitHub 令牌。
- `target_repository`: 目标仓库，格式为 owner/repo。
- `target_branch`: 需要同步的目标仓库分支。
- `upstream_repository`: 上游仓库，格式为 owner/repo。
- `upstream_branch`: 需要同步的上游仓库分支。

## 使用示例

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
