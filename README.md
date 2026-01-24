# Github Infrastructure

This repository contains various self-hosted services managed via Docker. The recommended deployment method is using **Portainer Stacks**.

## Service Stacks

| Stack | Description | Ports / Access |
|-------|-------------|----------------|
| **[Adguard Home](./Adguard%20Home)** | Network-wide ad blocker | DNS: `53` |
| **[Arr-Stack](./Arr-Stack)** | Media automation & Streaming | Jellyfin: `8096`, Sonarr: `8989`, Radarr: `7878`, etc. |
| **[Monitoring](./Monitoring)** | Prometheus & Grafana | Grafana: `3000`, Prometheus: `9090` |
| **[Navidrome](./Navidrome)** | Music streaming server | Tailscale only |
| **[Tidaloader](./Tidaloader)** | Tidal music downloader | `8275` |
| **[Watchtower](./Watchtower)** | Automatic container updates | N/A |
| **[n8n](./n8n)** | Workflow automation | `5678` |

## Port Reference Table

| Service | Port | Description |
|---------|------|-------------|
| Adguard Home | 53 | DNS Service |
| Grafana | 3000 | Monitoring Dashboard |
| Prometheus | 9090 | Metrics Database |
| n8n | 5678 | Automation Platform |
| Jellyfin | 8096 | Media Server |
| Sonarr | 8989 | TV Show Management |
| Radarr | 7878 | Movie Management |
| Prowlarr | 9696 | Indexer Management |
| qBittorrent | 8080 | Torrent Client |
| Tidaloader | 8275 | Music Downloader |
| cAdvisor | 8081 | Container Metrics |
| Node Exporter | 9100 | Host Metrics |
| FlareSolverr | 8191 | Solves Cloudflare Challenges |
| Requestrr | 4545 | Media Requests |

## Deployment (Portainer)

1. Open Portainer and go to **Stacks** > **Add stack**.
2. Give the stack a name.
3. Copy the content of the stack's `docker-compose.yml` into the **Web editor**.
4. Define environment variables in the **Environment variables** section (using "Advanced mode" to paste the `.env` content).
5. Click **Deploy the stack**.
