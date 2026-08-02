FROM ghcr.io/actions/actions-runner:2.336.0

USER root

RUN apt-get update -y \
  && apt-get install -y --no-install-recommends ca-certificates curl gnupg \
  && curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg \
  | dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg bs=8192 count=1 status=none \
  && chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
  && echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" \
  > /etc/apt/sources.list.d/github-cli.list \
  && apt-get update -y \
  && apt-get install -y --no-install-recommends gh \
  && rm -rf /var/lib/apt/lists/*

USER runner
