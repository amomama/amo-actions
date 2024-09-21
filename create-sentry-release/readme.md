# Create Sentry Release
Automatically create a Sentry release in a workflow

## Inputs

### `sentry-project` (required)
Project name in Publishing organization

## Example Usage

```yaml
jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Create Sentry Release
        uses: amomama/amo-actions/create-sentry-release@v5.0.0
        with:
          service-name: 'measuremonitor'
```
