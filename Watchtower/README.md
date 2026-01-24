# Watchtower

Automatic Docker container updates.

## Deployment with Portainer

1. Create a new **Stack** in Portainer.
2. Copy the contents of [`docker-compose.yml`](./docker-compose.yml) into the Portainer Web Editor.
3. Click **Load variable from .env file** in the **Environment variables** section and upload the [`.env`](./.env) file.
4. Deploy the stack.

## Services

- **watchtower**: Monitors other containers for updates.

## Configuration

Required environment variables in `.env`:

| Variable | Description |
|----------|-------------|
| `TZ` | Timezone (default: `Asia/Kolkata`) |
