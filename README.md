# Gearbox Action

Gearbox 的 Marketplace 发布仓。

这个仓库由主开发仓 `gqy20/gearbox` 自动导出，用于提供稳定、轻量的 GitHub Action 对外入口。

## 用法

```yaml
- uses: gqy20/gearbox-action@v1
  with:
    action: audit
    repo: ${{ github.repository }}
    anthropic_api_key: ${{ secrets.ANTHROPIC_AUTH_TOKEN }}
```

这是推荐给大多数用户的接入方式。action 会负责准备运行环境、克隆目标仓库、执行扫描并调用 Gearbox Agent。

需要真正的 matrix 并行、artifact 聚合和多实例选优时，请参考主开发仓中的 workflow 编排，或使用保留的 reusable workflow 模板：

```yaml
jobs:
  audit:
    uses: gqy20/gearbox/.github/workflows/reusable-audit.yml@main
    with:
      repo: owner/repo
      parallel_runs: '3'
      create_issues: false
    secrets: inherit
```

## 支持的动作

- `audit`
- `backlog`
- `implement`
- `cleanup`
- `dispatch`
- `review`
- `publish`

## 发布说明

版本更新记录见 `CHANGELOG.md`。每个 GitHub Release 的说明都从主开发仓的对应版本段落自动提取。

## 仓库说明

- 主开发仓：`gqy20/gearbox`
- 当前仓库：面向 Marketplace 的发布产物
- 如需修改功能、提 issue 或提交代码，请回到主开发仓进行
