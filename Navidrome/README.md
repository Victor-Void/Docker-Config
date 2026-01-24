# Navidrome

Self-hosted music streamer with Tailscale integration.

## Deployment with Portainer

1. Create a new **Stack** in Portainer.
2. Copy the contents of [`docker-compose.yml`](./docker-compose.yml) into the Portainer Web Editor.
3. Click **Load variable from .env file** in the **Environment variables** section and upload the [`.env`](./.env) file.
4. Deploy the stack.

## Services

- **tailscale**: Connects Navidrome to your private network.
- **application**: The Navidrome server instance.

## Configuration

Required environment variables in `.env`:

| Variable | Description |
|----------|-------------|
| `SERVICE` | Tailscale hostname |
| `TS_AUTHKEY` | Tailscale Auth Key |
| `TS_CERT_DOMAIN` | Tailscale domain for certs |
| `IMAGE_URL` | Navidrome image |
| `LASTFM_APIKEY` | Last.fm API Key |
| `LASTFM_SECRET` | Last.fm API Secret |
