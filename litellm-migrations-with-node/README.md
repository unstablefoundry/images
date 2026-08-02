# litellm-migrations-with-node

Upstream [`ghcr.io/berriai/litellm-migrations`](https://github.com/BerriAI/litellm) with Node/nodeenv pre-baked for Prisma.

Upstream runs `prisma migrate deploy` with a 60s hard timeout. On arm64, first-boot `nodeenv` often exceeds that and the Job fails. This image installs nodeenv at build time so migrate can run immediately. Entrypoint/CMD are unchanged.

Published tag tracks the upstream migrations image version (no `VERSION` file). Keep in lockstep with the LiteLLM Helm chart version.

## Pull

```bash
docker pull ghcr.io/unstablefoundry/images/litellm-migrations-with-node:latest
```

## Use with LiteLLM Helm

```yaml
migrationJob:
  enabled: true
  image:
    repository: ghcr.io/unstablefoundry/images/litellm-migrations-with-node
    tag: "latest"
```
