# Invalidate CloudFront with retries

## Inputs

```
  distribution:
    description: "CloudFront Distribution ID"
    required: true
  retrying:
    description: "Retrying count"
    required: false
    default: 1
```

## Example Usage

```
- name: Invalidate CloudFront
  uses: your-org/your-repo/.github/actions/invalidate-cloudfront@main
  with:
    distribution-id: E2M8ILOBF84EDF
    retrying: 3
```