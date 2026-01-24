# Arr-Stack (Media Server)

A comprehensive media automation and streaming stack.

## Deployment with Portainer

1. Create a new **Stack** in Portainer.
2. Copy the contents of [`docker-compose.yml`](./docker-compose.yml) into the Portainer Web Editor.
3. Click **Load variable from .env file** in the **Environment variables** section and upload the [`.env`](./.env) file.
4. Deploy the stack.

## Services & Ports

- **jellyfin**: `8096`
- **sonarr**: `8989`
- **radarr**: `7878`
- **prowlarr**: `9696`
- **qbittorrent**: `8080`
- **flaresolverr**: `8191`
- **requestrr**: `4545`

## Configuration

Required environment variables in `.env`:

| Variable | Description |
|----------|-------------|
| `TS_AUTHKEY` | Tailscale Authentication Key |
