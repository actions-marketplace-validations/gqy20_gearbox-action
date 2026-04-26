# Gearbox Action

Marketplace-facing release repository for Gearbox.

This repository is generated from the main development repository and is intended
to provide a stable GitHub Action entrypoint for external consumers.

## Usage

```yaml
- uses: gqy20/gearbox-action@v1
  with:
    action: audit
    repo: ${{ github.repository }}
    anthropic_api_key: ${{ secrets.ANTHROPIC_AUTH_TOKEN }}
```

## Supported actions

- `audit`
- `triage`
- `implement`
- `review`
- `publish`

## Source of truth

Development happens in the main `gearbox` repository. This bundle is exported for
release and Marketplace publication.
