# Create Release PR into Master from Stage

This GitHub Action automates the process of creating a pull request (PR) to merge changes from the `stage` branch into the `master` branch, effectively releasing the changes.

## Inputs

### `gh-token` (required)

The GitHub token used for authentication. This token should have the necessary permissions to create a PR.

## Example Usage

```yaml
name: 'Create Release PR into master from stage'

on:
  workflow_dispatch:

jobs:
  create-pr:
    runs-on: ubuntu-latest

    steps:
      - name: Create Release PR
        uses: your-repo/create-release-pr-action@v1.0.0
        with:
          gh-token: ${{ secrets.GITHUB_TOKEN }}
