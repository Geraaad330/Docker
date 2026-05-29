# 🐳 HomeLab Docker Collection

This repository contains a collection of `docker-compose` configuration files for my HomeLab. 
Most services are hosted on a **Raspberry Pi 5** and a **GL.iNet Flint 2** router, creating a cohesive ecosystem for network management, media, and home automation.

## 📂 Structure and Service Categories

Below is a list of services available in this repository, divided into functional categories.

### 🌐 Network & Security
Core services ensuring security, remote access, and ad blocking.

| Service | Compose File | Description |
| :--- | :--- | :--- |
| **Nginx Proxy Manager** | `docker-compose_npm.yaml` | SSL certificate management and Reverse Proxy for all services. |
| **AdGuard Home** | `docker-compose_adguard.yaml` | DNS server with network-wide ad and tracker blocking. |
| **Vaultwarden** | `docker-compose_vaultwarden.yaml` | Lightweight Bitwarden server for secure password management. |
| **Glass / DHCP** | `docker-compose_glass-dhcp.yaml` | DHCP server / IP address management. |

### ☁️ Cloud & Storage
Data storage, file synchronization, and backups.

| Service | Compose File | Description |
| :--- | :--- | :--- |
| **Nextcloud** | `docker-compose_nextcloud.yaml` | Private cloud for files, calendar, and contacts. |
| **Syncthing** | `docker-compose_syncthing.yaml` | P2P file synchronization between devices. |
| **Duplicati** | `docker-compose_duplicati.yaml` | Automated, encrypted data backups. |
| **JDownloader 2** | `docker-compose_JDownloader2.yaml` | Web-browser accessible file download manager. |

### 📺 Media & Entertainment
Multimedia center.

| Service | Compose File | Description |
| :--- | :--- | :--- |
| **Jellyfin** | `docker-compose_jellyfin.yaml` | Media server (movies, TV shows) - an alternative to Plex/Emby. |

### 📊 Monitoring & Tools
Server health maintenance and notifications.

| Service | Compose File | Description |
| :--- | :--- | :--- |
| **Portainer** | `docker-compose_portainer.yaml` | Graphical User Interface (GUI) for Docker management. |
| **Uptime Kuma** | `docker-compose_uptime_kuma.yaml` | Service uptime monitoring (status page). |
| **Speedtest Tracker**| `docker-compose_speedtest_tracker.yaml` | Automated internet speed testing and history charts. |
| **Checkmk** | `docker-compose_checkmk.yaml` | Advanced IT infrastructure monitoring system. |
| **Diun** | `docker-compose_diun.yaml` | (Docker Image Update Notifier) Notifications about new image versions. |
| **Gotify** | `docker-compose_gotify.yaml` | Self-hosted push notification server. |
| **Ofelia** | `ofelia/` & `docker-compose_ofelia.yaml` | Task scheduler (Cron replacement) for container management. |
| **Monitoring Stack** | `monitoring/` | Prometheus + Grafana stack for metrics visualization. |

### 🏠 Smart Home & Office
Automation and productivity.

| Service | Compose File | Description |
| :--- | :--- | :--- |
| **Node-RED** | `docker-compose_node_red.yaml` | Tool for wiring together hardware devices, APIs, and online services (automations). |
| **Collabora** | `docker-compose_collabora.yaml` | Online office suite (Nextcloud integration). |
| **Firefox** | `docker-compose_firefox.yaml` | Web browser running in a container. |

## 🚀 How to Use

Each YAML file is independent (or part of a larger stack). To start a selected service:

```bash
# Example for AdGuard Home
docker compose -f docker-compose_adguard.yaml up -d

# Example for Portainer
docker compose -f docker-compose_portainer.yaml up -d
