# Invalidate CloudFront with retries

## Inputs

```
  distribution:
    description: "CloudFront Distribution ID or multiple IDs separated by comma/space/newline"
    required: true
  retrying:
    description: "Retry count per distribution"
    required: false
    default: 1
```

## Example Usage

### For one
```
- name: Invalidate CloudFront
  uses: your-org/your-repo/.github/actions/invalidate-cloudfront@v8.0.0
  with:
    distribution: E2M8ILOBF84EDF
    retrying: 3
```

### For many
```
- name: Invalidate CloudFront
  uses: your-org/your-repo/.github/actions/invalidate-cloudfront@v8.0.0
  with:
    distribution: "EPIJXYZ88VKBF E1ABCDEF999999 E3EXAMPLE888888"
    retrying: 3
```
OR
```
- name: Invalidate CloudFront
  uses: your-org/your-repo/.github/actions/invalidate-cloudfront@v8.0.0
  with:
    distribution: "EPIJXYZ88VKBF,E1ABCDEF999999,E3EXAMPLE888888"
    retrying: 3
```
OR
```
- name: Invalidate multiple CloudFront
  uses: amomama/amo-actions/invalidate-cloudfront@v8.0.0
  with:
    distribution: |
        EPIJXYZ88VKBF
        E1ABCDEF999999
        E3EXAMPLE888888
    retrying: 3
```