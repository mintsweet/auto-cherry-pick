# Auto Cherry Pick

A GitHub Action that automatically cherry pick.

## What does it do?

This GitHub Action to help you:

- Auto-create a new PR from a merged PR with a specific label.
- Auto-assign specific labels for the original PR.
- Auto-assign bot comment for the original PR.
- Auto-assign title and body for the new PR.
- Auto-assign specific labels for the new PR.
- Auto-assign bot comment for the new PR.

## Example

```yml
name: Auto Cherry Pick

on:
  pull_request:
    types:
      - labeled
      - closed

jobs:
  cherry-pick:
    if: github.event.pull_request.merged == true
    runs-on: ubuntu-latest
    permissions:
      contents: write
      pull-requests: write
    steps:
      - uses: actions/checkout@v3
      - name: Auto Cherry Pick
        uses: mintsweet/auto-cherry-pick@v1.0.0
```

## LICENSE

[MIT](./LICENSE)
