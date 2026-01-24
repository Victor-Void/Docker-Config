# n8n

n8n is an extendable workflow automation tool.

## Deployment with Portainer

1. Create a new **Stack** in Portainer.
2. Copy the contents of [`docker-compose.yml`](./docker-compose.yml) into the Portainer Web Editor.
3. Click **Load variable from .env file** in the **Environment variables** section and upload the [`.env`](./.env) file.
4. Deploy the stack.

## Services

- **n8n**: The workflow automation engine reachable on port `5678`.

## Configuration

Required environment variables in `.env`:

| Variable | Description |
|----------|-------------|
| `USERNAME` | Basic auth username (default: `admin`) |
| `PASSWORD` | Basic auth password |
