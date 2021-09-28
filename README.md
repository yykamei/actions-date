# actions-date

A composite GitHub Actions that outputs datetime with date(1)

```yaml
name: Test
on:
  push:
    branches: [main]
  workflow_dispatch:
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - id: default
        uses: yykamei/actions-date@main
      - id: with-format
        uses: yykamei/actions-date@main
        with:
          format: '%Y-%m-%dT%H:%M:%S'
      - run: echo '${{ steps.default.outputs.date }}'
      - run: echo '${{ steps.with-format.outputs.date }}'
```
