# Deploy Status Action
This action is designed to send a notification to a Slack channel based on the status of a deployment job. It is particularly useful for keeping your team informed about the deployment outcome.

## Inputs

### `slack-webhook-url` (required)
The Slack incoming webhook URL to which the notification will be sent. You can use integrations similar to [Incoming WebHooks](https://quivomedia.slack.com/apps/A0F7XDUAZ-incoming-webhooks?tab=more_info).

### `status` (required)
The status of the deployment job. This can be either "success" or "failure."

### `app-url` (required)
The URL of the deployed application.

### `get-parameter` (optional)
An optional parameter that can be appended to the `app-url` for additional customization.

## Example Usage

```yaml
jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Deploy Status Notification
        uses: your-repo/sync-argocd-action@v4.0.1
        with:
          slack-webhook-url: ${{ secrets.SLACK_WEBHOOK_URL }}
          status: ${{ job.status }}
          app-url: 'your-app-url.com'
          get-parameter: "?version=1.0"
```

In the example above, the action checks out the code and then sends a message to the specified Slack channel.
This action operates as a composite, relying on [action-slack](https://github.com/8398a7/action-slack/). The content of the message is determined based on the deployment status:

<img src="https://github.com/amomama/amo-actions/assets/85172571/fd019a34-1503-4a6b-af8d-ea029dd5e571" width="500"/>
