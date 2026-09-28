# actions-runner/gh-cli

Runner image based on [`ghcr.io/actions/actions-runner`](https://github.com/actions/runner/pkgs/container/actions-runner), for use with [Actions Runner Controller](https://docs.github.com/en/actions/concepts/runners/actions-runner-controller).

Installed on top of the base image:

- [GitHub CLI](https://cli.github.com/) (`gh`)
- [mikefarah/yq](https://github.com/mikefarah/yq)

Published tag tracks the upstream runner version (no `VERSION` file). `:latest` tracks the newest build on `main`.

## Pull

```bash
docker pull ghcr.io/unstablefoundry/images/actions-runner/gh-cli:latest
```

## Use with ARC

```yaml
template:
  spec:
    containers:
      - name: runner
        image: ghcr.io/unstablefoundry/images/actions-runner/gh-cli:latest
        command: ["/home/runner/run.sh"]
```
