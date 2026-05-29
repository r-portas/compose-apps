# nginx-static

Serves a single static HTML page with nginx. The simplest possible Compose stack — one service, one bind-mounted file.

## Compose features demonstrated

- Single-service stack
- Bind mount for a config/content file
- Health check
- `restart: unless-stopped`
- Port mapping via env var

## Usage

```bash
docker compose up -d
```

Open [http://localhost:8080](http://localhost:8080) (or whatever `HTTP_PORT` you set).

## Configuration

| Variable    | Default | Description                          |
| ----------- | ------- | ------------------------------------ |
| `HTTP_PORT` | `8080`  | Host port to expose the nginx server |

## First-run notes

No persistent data, no setup steps. To serve different content, edit `index.html` and restart the container:

```bash
docker compose restart web
```
