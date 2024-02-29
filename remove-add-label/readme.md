# Remove and Add Label on Pull Requests

This GitHub Actions composite action facilitates the removal and addition of a label on pull requests within your GitHub repository.

## Inputs

### `github-token` (required)
The GitHub token used for authentication and authorization purposes when interacting with the GitHub API.

### `label-name` (required)
The name of the label to remove from existing pull requests and add to the pull request that triggered the workflow.

## Example Usage
```yaml
jobs:
  manage-labels:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Remove and Add Label
        uses: your-repo/remove-add-label-action@v5.0.0
        with:
          github-token: ${{ secrets.GH_TOKEN }}
          label-name: 'Deployed'
```

In the example above, after checking out the code, the "Remove and Add Label" action is employed to remove the specified label from all open pull requests and add it to the pull request that triggered the workflow.

Please ensure that you have set up the necessary permissions and secrets to access the GitHub API and perform label management operations.