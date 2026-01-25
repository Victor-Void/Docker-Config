# GitHub Infrastructure

Self-hosted services managed via Docker and deployed through **Portainer Stacks**.

## Prerequisites

- Docker Engine and Docker Compose
- [Portainer](https://www.portainer.io/)
- [Tailscale](https://tailscale.com/) account and auth key

## Services Overview

| Stack | Description |
|-------|-------------|
| **[Adguard Home](./Adguard%20Home)** | Network-wide ad and tracker blocking |
| **[Arr-Stack](./Arr-Stack)** | Media automation and streaming suite |
| **[Monitoring](./Monitoring)** | Prometheus & Grafana monitoring |
| **[Navidrome](./Navidrome)** | Personal music streaming server |
| **[Tidaloader](./Tidaloader)** | Tidal music downloader |
| **[Watchtower](./Watchtower)** | Automatic container updates |
| **[n8n](./n8n)** | Workflow automation platform |

## Port Reference

| Service | Port | Access Method |
|---------|------|---------------|
| **Adguard Home** | 53 (DNS) | Tailscale HTTPS |
| **Grafana** | 3000 | `http://<host-ip>:3000` |
| **Prometheus** | 9090 | `http://<host-ip>:9090` |
| **n8n** | 5678 | `http://<host-ip>:5678` |
| **Jellyfin** | 8096 | `http://<host-ip>:8096` |
| **Sonarr** | 8989 | `http://<host-ip>:8989` |
| **Radarr** | 7878 | `http://<host-ip>:7878` |
| **Prowlarr** | 9696 | `http://<host-ip>:9696` |
| **qBittorrent** | 8080 | `http://<host-ip>:8080` |
| **Tidaloader** | 8275 | `http://<host-ip>:8275` |
| **cAdvisor** | 8081 | `http://<host-ip>:8081` |
| **Node Exporter** | 9100 | `http://<host-ip>:9100` |
| **FlareSolverr** | 8191 | `http://<host-ip>:8191` |
| **Requestrr** | 4545 | `http://<host-ip>:4545` |
| **Navidrome** | N/A | Tailscale only |

## Environment Variables

Common variables required for Tailscale-enabled services:

- `TS_AUTHKEY` - Tailscale authentication key
- `TS_CERT_DOMAIN` - Your Tailscale domain (e.g., `service.tailnet-xxxx.ts.net`)
- `SERVICE` - Service identifier
- `IMAGE_URL` - Docker image for the application
- `TZ` - Timezone (e.g., `Asia/Kolkata`)

Check individual service directories for specific requirements.

## Deployment (Portainer)

1. Open Portainer and navigate to **Stacks** → **Add stack**
2. Enter a stack name
3. Copy the service's `docker-compose.yml` into the **Web editor**
4. Add environment variables in **Environment variables** section (use **Advanced mode** for bulk paste)
5. Click **Deploy the stack**

## Troubleshooting

**Service won't start:**
- Check container logs in Portainer
- Verify all required environment variables are set
- Ensure volume paths exist with correct permissions

**Can't access Tailscale services:**
- Verify you're connected to Tailscale network
- Check `TS_CERT_DOMAIN` matches your actual domain
- Confirm Tailscale container is running and healthy

**DNS not working (Adguard Home):**
- Confirm port 53 is not in use by another service
- Verify container has `net_admin` capability

