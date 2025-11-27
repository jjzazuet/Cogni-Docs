# Instructions for Pushing Docker Images to GitHub Container Registry

The Docker images have been built and tagged, but need to be pushed to GitHub Container Registry. You'll need to authenticate first.

## Authentication

1. Create a GitHub Personal Access Token (PAT) with `write:packages` permission:
   - Go to: https://github.com/settings/tokens
   - Generate new token (classic)
   - Select scope: `write:packages`

2. Login to GitHub Container Registry:
   ```bash
   echo $GITHUB_TOKEN | docker login ghcr.io -u jjzazuet --password-stdin
   ```
   Or interactively:
   ```bash
   docker login ghcr.io -u jjzazuet
   ```

## Push Images

Once authenticated, push the images:

```bash
docker push ghcr.io/jjzazuet/cogni-docs/mcp-server:latest
docker push ghcr.io/jjzazuet/cogni-docs/web-ui:latest
```

## Make Images Public (Optional)

After pushing, make the packages public if needed:
- Go to: https://github.com/jjzazuet?tab=packages
- Select each package
- Package settings → Change visibility → Public

