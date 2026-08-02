# images

Container images published to `ghcr.io/<owner>/<repo>/<image-path>:<tag>` (also `:latest` on `main`).

Each image is a folder with a `Dockerfile` (nesting allowed; path = image name). See that folder’s `README.md` for image-specific details.

## Use an image

```bash
docker pull ghcr.io/unstablefoundry/images/<image-path>:<tag>
```

Example: `ghcr.io/unstablefoundry/images/actions-runner/gh-cli:latest`

## Add an image

1. Create `<path>/Dockerfile` and `<path>/README.md`.
2. Choose versioning:
   - **Mirror upstream** — no `VERSION` file; the published tag comes from the first `FROM …:tag`.
   - **Own version** — add `<path>/VERSION` (e.g. `0.1.0`) and register the path in `release-please-config.json` and `.release-please-manifest.json`:

```json
"path/to/image": {
  "release-type": "simple",
  "version-file": "VERSION",
  "package-name": "path-to-image"
}
```

Push to `main` (or open a PR) to test/build; changed image folders are discovered automatically.
