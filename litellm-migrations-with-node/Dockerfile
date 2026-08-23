FROM ghcr.io/berriai/litellm-migrations:v1.98.0

USER root

RUN /app/.venv/bin/python -m nodeenv /home/nonroot/.cache/prisma-python/nodeenv \
  && chown -R 65532:65532 /home/nonroot/.cache

USER 65532

ENV PATH="/home/nonroot/.cache/prisma-python/nodeenv/bin:${PATH}"
