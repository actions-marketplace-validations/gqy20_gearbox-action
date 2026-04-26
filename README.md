# Gearbox Action

Gearbox 的 Marketplace 发布仓。

这个仓库由主开发仓自动导出，用于提供稳定的 GitHub Action 对外入口。

## 用法

```yaml
- uses: gqy20/gearbox-action@v1
  with:
    action: audit
    repo: ${ github.repository }
    anthropic_api_key: ${ secrets.ANTHROPIC_AUTH_TOKEN }
```

## 支持的动作

- `audit`
- `triage`
- `implement`
- `review`
- `publish`

## 仓库说明

- 主开发仓：`gqy20/gearbox`
- 当前仓库：面向 Marketplace 的发布产物
- 如需修改功能、提 issue 或提交代码，请回到主开发仓进行
