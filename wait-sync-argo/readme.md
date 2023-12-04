# Sync ArgoCD Application

This GitHub Actions composite action allows you to synchronize an ArgoCD application by wrapping the necessary steps in a single composite action. It syncs a specified ArgoCD application by downloading the ArgoCD CLI, waiting for the operation and health status, and performing the synchronization.

## Inputs

### `cli-version` (required)
The version of the ArgoCD CLI to download. It is used to construct the download URL for the ArgoCD CLI binary.

### `app-name` (required)
The name of the ArgoCD application to synchronize.

### `auth-token` (required)
The authentication token to use when communicating with the ArgoCD server.

### `argo-server` (required)
The URL of the ArgoCD server.

## Example Usage

```yaml
jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Sync ArgoCD Application
        uses: your-repo/sync-argocd-action@v3.0.1
        with:
          cli-version: '2.0.1'
          app-name: 'my-argocd-app'
          auth-token: ${{ secrets.ARGOCD_TOKEN }}
          argo-server: 'https://argocd.example.com'
```

In the example above, the action checks out the code, and then the "Sync ArgoCD Application" action is used to synchronize the specified ArgoCD application.

Please ensure that you have set up the necessary secrets and permissions to use the ArgoCD CLI and authenticate with your ArgoCD server.
