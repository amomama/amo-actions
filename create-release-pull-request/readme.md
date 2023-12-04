# Create Release PR into Master from Stage

This GitHub Action automates the process of creating a pull request (PR) to merge changes from the `stage` branch into the `master` branch, effectively releasing the changes.

## Inputs

### `gh-token` (required)

The GitHub token used for authentication. This token should have the necessary permissions to create a PR.

### `description` (required)

Uses for filling description part of PR, e.g. name of released features, steps to check

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
        uses: your-repo/create-release-pull-request@v3.0.1
        with:
          gh-token: ${{ secrets.GITHUB_TOKEN }}
          description: "Description:\n \n- [ ] Functional tests checked\n- [ ] Devices tests checked"
