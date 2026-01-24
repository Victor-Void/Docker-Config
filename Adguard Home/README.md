# Adguard Home

Network-wide ad blocker with Tailscale integration.

## Deployment with Portainer

1. Create a new **Stack** in Portainer.
2. Copy the contents of [`docker-compose.yml`](./docker-compose.yml) into the Portainer Web Editor.
3. Click **Load variable from .env file** in the **Environment variables** section and upload the [`.env`](./.env) file.
4. Deploy the stack.

## Services & Ports

- **tailscale**: Private network connectivity.
- **adguard-home**: Admin interface on port `9433` (as configured), DNS on port `53`.

## Configuration

Required environment variables in `.env`:

| Variable | Description |
|----------|-------------|
| `SERVICE` | Name of the service |
| `TS_AUTHKEY` | Tailscale Authentication Key |
| `TS_CERT_DOMAIN` | Tailscale domain for HTTPS |
| `IMAGE_URL` | Adguard Home image |
