FROM ghcr.io/actions/actions-runner:2.338.0

USER root

# hadolint ignore=DL3008
RUN apt-get update -y \
  && apt-get install -y --no-install-recommends ca-certificates curl gnupg \
  && curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg \
    -o /usr/share/keyrings/githubcli-archive-keyring.gpg \
  && chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
  && echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" \
  > /etc/apt/sources.list.d/github-cli.list \
  && apt-get update -y \
  && apt-get install -y --no-install-recommends gh \
  && rm -rf /var/lib/apt/lists/*

USER runner
