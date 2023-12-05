# Create After Release PR into Stage from Master

This GitHub Action automates the process of creating a pull request (PR) to merge changes from the `master` branch into the `stage` branch, after release.

## Inputs

### `gh-token` (required)

The GitHub token used for authentication. This token should have the necessary permissions to create a PR.

## Example Usage

```yaml
name: 'Create PR master to stage'

on:
  push:
    branches:
      - master

jobs:
  create-pr:
    runs-on: ubuntu-latest

    steps:
      - name: Create PR
        uses: your-repo/pull-master-to-stage@v4.0.0
        with:
          gh-token: ${{ secrets.GITHUB_TOKEN }}
