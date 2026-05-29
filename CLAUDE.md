# CLAUDE.md — AI Agent Instructions

## Repository layout

Each app lives in its own top-level directory. No shared code between apps.

## Compose file conventions

- Name files `compose.yaml`, never `docker-compose.yml`
- Pin image tags to a specific version (not `latest`)
- Always set `restart: unless-stopped` on long-running services
- Use explicit named networks; do not rely on the default network

## Secrets and environment variables

- All sensitive values go in `.env` (gitignored)
- Never commit real secrets

## Volumes

- Use named volumes for persistent data
- Bind mounts are acceptable only for config files that belong in the repo (e.g. `nginx.conf`, `index.html`)

## Health checks and dependencies

- Prefer health checks on services that other services depend on
- Use `depends_on: condition: service_healthy` rather than bare `depends_on`

## Per-app README

Every app directory must contain a `README.md` that covers:
1. What the app is and what it does
2. How to start it (`docker compose up -d`)
3. Default ports and URLs
4. Any first-run setup steps (e.g. initial admin password, volume seeding)
