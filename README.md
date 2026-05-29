# compose-apps

A curated collection of Docker Compose application stacks for self-hosting and homelab use. Each app is self-contained, production-ready, and demonstrates a specific set of Compose features.

## Apps

| Directory | App | Description | Compose features |
|---|---|---|---|
| [`nginx-static/`](nginx-static/) | nginx static site | nginx serving a custom `index.html` | bind mount, health check, port via env var |

## Getting started

Every app follows the same pattern:

```bash
cd <app-directory>
docker compose up -d
```

Check the app's `README.md` for the default URL, ports, and any first-run setup.

## Conventions

- Compose files are named `compose.yaml`
- Persistent data uses named volumes; config files use bind mounts
- Health checks are included wherever meaningful
- Secrets stay in `.env` (gitignored)
