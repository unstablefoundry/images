# actions-runner/gh-cli

[Actions Runner Controller](https://docs.github.com/en/actions/concepts/runners/actions-runner-controller) runner image based on [`ghcr.io/actions/actions-runner`](https://github.com/actions/runner/pkgs/container/actions-runner), with [GitHub CLI](https://cli.github.com/) (`gh`) installed.

Published tag tracks the upstream runner version (no `VERSION` file).

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
