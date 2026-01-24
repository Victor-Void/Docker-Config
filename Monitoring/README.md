# Monitoring Stack

A full monitoring suite using Prometheus, Grafana, Node Exporter, and cAdvisor.

## Deployment with Portainer

1. Create a new **Stack** in Portainer.
2. Copy the contents of [`docker-compose.yml`](./docker-compose.yml) into the Portainer Web Editor.
3. Click **Load variable from .env file** in the **Environment variables** section and upload the [`.env`](./.env) file.
4. Deploy the stack.

## Services & Ports

- **grafana**: `3000`
- **prometheus**: `9090`
- **cadvisor**: `8081`
- **node-exporter**: `9100`

## Configuration

Required environment variables in `.env`:

| Variable | Description |
|----------|-------------|
| `USER` | Grafana admin username |
| `PASSWORD` | Grafana admin password |
