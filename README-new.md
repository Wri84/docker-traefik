# 🐳 Ultimate Docker Homelab Setup

> **Real-world Docker configurations** from Anand at [SimpleHomelab.com](https://www.simplehomelab.com/) (formerly SmartHomeBeginner.com)

[![Deployrr](https://img.shields.io/badge/Powered%20by-Deployrr-blue?style=flat-square)](https://www.simplehomelab.com/deployrr/)
[![UDMS Series](https://img.shields.io/badge/UDMS-Series-green?style=flat-square)](https://www.simplehomelab.com/ultimate-docker-media-server-udms-01/)
[![150+ Apps](https://img.shields.io/badge/Apps-150%2B-orange?style=flat-square)](#-featured-applications)

---

## 🎯 What This Repository Offers

This repository contains my **actual production Docker setups** that power my homelab infrastructure. Unlike theoretical guides, these are real-world configurations that I use daily.

### ✨ Key Features
- **Real-world configurations** based on [Deployrr](https://www.simplehomelab.com/deployrr/) and [Ultimate Docker Media Server](https://www.simplehomelab.com/ultimate-docker-media-server-udms-01/) series
- **150+ Docker applications** ready to deploy
- **Multi-host architecture** spanning home servers, cloud VPS, and NAS
- **Production-tested** setups with security and performance optimizations
- **Extensive documentation** and video tutorials

### 🎯 Repository Purpose
1. **Share actual setups** - Real configurations I use in production
2. **Extend Deployrr capabilities** - Examples beyond standard Deployrr templates
3. **Provide advanced configurations** - Complex setups not covered in basic guides

---

## 🖥️ Infrastructure Overview

I believe in **simple, energy-efficient homelab** design that maximizes performance while minimizing complexity.

### 🏠 Home Network Architecture
- **OPNsense** firewall running on Proxmox VM
- **Tailscale** mesh networking connecting all hosts
- **Multi-tier deployment** across different hardware platforms

### 📊 Hardware Specifications

| Component | Specifications | Purpose |
|-----------|---------------|---------|
| **TopTon V700 Mini PC** | Intel i7-13800H, 64GB RAM, 2×2TB NVMe ZFS RAID1, 4TB SATA SSD | Primary Proxmox host |
| **Synology DS918+** | DX517 Expansion, 8GB RAM, 4×18TB SHR2 (×2 volumes) | Storage & legacy apps |
| **Oracle Ampere A1** | 4 vCPU ARM64, 24GB RAM, 200GB storage | Web server & ARM workloads |

---

## 🐳 Docker Hosts

All Docker configurations are organized by host with clear naming conventions:

### 🏠 Home Server (`hs-*`)
```yaml
Platform: Ubuntu 24.04 LXC on Proxmox
Resources: 8 vCPU, 8GB RAM, 4GB Swap
Storage: 64GB OS + 32GB Docker data
Purpose: Core homelab services
```

### 🎬 Media Database Server (`mds-*`)
```yaml
Platform: Ubuntu 24.04 LXC on Proxmox  
Resources: 12 vCPU, 12GB RAM, 4GB Swap
Storage: 64GB OS + 72GB Docker data
Purpose: Media management & processing
```

### 🌐 Web Server (`ws-arm-*`)
```yaml
Platform: Ubuntu 24.04 ARM64 on Oracle Cloud
Resources: 4 vCPU, 24GB RAM
Storage: 100GB OS + 100GB data
Purpose: Web applications & ARM workloads
```

### 💾 Synology NAS (`ds918-*`)
```yaml
Platform: DSM 7.2
Resources: 8GB RAM, 144TB storage (SHR2)
Purpose: Storage & legacy applications
```

### 📁 Archives
Legacy configurations in `_archives_` folder - not actively maintained but useful as reference.

---

## 📚 Learning Resources

### 🎥 Ultimate Docker Media Server Series

**Complete step-by-step guide** to building a professional Docker homelab:

#### 🚀 Getting Started
1. [Introduction and Overview](https://www.simplehomelab.com/udms-01-introduction-and-overview/)
2. [Hardware: NAS, Mini PC, or VPS (FREE!). Which one?](https://www.simplehomelab.com/udms-02-hardware-nas-minipc-vps/)
3. [Best Home Server OS, Proxmox LXC vs VM](https://www.simplehomelab.com/udms-03-best-home-server-os/)

#### ⚙️ Infrastructure Setup
4. [Install Proxmox on Mini PC with ZFS RAID1 Mirror + 3 Tweaks](https://www.simplehomelab.com/udms-04-install-proxmox-on-mini-pc/) [📹](https://youtu.be/2nIPY7D-UA0)
5. [Installing and Prepping Ubuntu/Debian](https://www.simplehomelab.com/udms-05-installing-ubuntu-on-proxmox/) [📹](https://youtu.be/-ZSQdJ62r-Q)
6. [Mounting Remote Folders using Rclone](https://youtu.be/D-XS0biLP14) [📹]
7. Mounting Remote Folders using SMB/CIFS *(Coming Soon)*
8. Mounting Remote Folders using NFS *(Coming Soon)*
9. Binding Mounting on Proxmox Unprivileged LXC *(Coming Soon)*

#### 🔧 Advanced Configuration
10. [Proxmox Unprivileged LXC Network Node Passthrough](https://www.simplehomelab.com/udms-10-proxmox-lxc-network-device-passthrough/) [📹](https://youtu.be/r0nGMFs5pCY)
11. [Proxmox Unprivileged LXC iGPU Node Passthrough](https://www.simplehomelab.com/udms-11-gpu-passthrough-on-proxmox-lxc/) [📹](https://youtu.be/kvnJYyyLoIk)

#### 🐳 Docker Fundamentals
12. [Installing Docker and Docker Compose on Ubuntu/Debian](https://www.simplehomelab.com/udms-12-install-docker-and-docker-compose/)
13. [Essential Docker Commands & Time-Saving Aliases](https://www.simplehomelab.com/udms-13-docker-and-docker-compose-commands/)
14. [Kickass Docker Media Server with 150+ Apps](https://www.simplehomelab.com/udms-14-docker-media-server/) [📹](https://youtu.be/THuLgGwq0vg)
15. Best Docker Containers for Homelab *(Coming Soon)*

#### 🌐 Remote Access & Security
16. [Exposing Apps to the Internet: Tailscale](https://www.simplehomelab.com/udms-part-16-tailscale-homelab-remote-access/) [📹](https://youtu.be/M6GMp4FJrB8)
17. Exposing Apps to the Internet: Nginx Proxy Manager *(Coming Soon)*
18. [Exposing Apps to the Internet: Traefik Reverse Proxy](https://www.simplehomelab.com/udms-18-traefik-docker-compose-guide/) [📹](https://www.youtube.com/playlist?list=PL1Hno7tIbSWUGrZSqeB9aCsdAuoeVwvgh)

#### 🔐 Authentication & Security
19. [Authentication for Docker Apps - Authelia](https://www.simplehomelab.com/udms-19-authelia-docker-compose/) [📹](https://youtu.be/UIq8PLZHBtk)
20. [Authentication for Docker Apps - Google OAuth 2](https://youtu.be/SCKALXprTQE) [📹]
21. [Authentication for Docker Apps - Authentik](https://youtu.be/GoUmJAe1MKc) [📹]
22. [CrowdSec Docker Compose – Bulletproof IPS for Homelabs](https://www.simplehomelab.com/udms-22-crowdsec-docker-compose/)
23. [Setting up Crowdsec Cloudflare Bouncer](https://www.simplehomelab.com/udms-23-crowdsec-cloudflare-bouncer/)
24. [Setting up Crowdsec Traefik Bouncer](https://www.simplehomelab.com/udms-24-crowdsec-traefik-bouncer/)

#### 🚀 Advanced Topics
25. Advanced Topics: Traefik Plugins *(Coming Soon)*
26. Advanced Topics: Traefik Multiple Domains *(Coming Soon)*
27. Advanced Topics: Traefik Domain Passthrough *(Coming Soon)*
28. Advanced Topics: [Traefik Conditional Auth Bypass](https://www.simplehomelab.com/udms-28-traefik-auth-bypass/)
29. Advanced Topics: [CrowdSec Multiserver Setup](https://www.simplehomelab.com/udms-29-crowdsec-multiserver/)
30. Closing Thoughts and Options to Level Up *(Coming Soon)*

### 📖 Additional Guides

#### 🏢 Synology NAS
- [Ultimate Synology NAS Docker Compose Media Server 2022](https://www.simplehomelab.com/synology-nas-docker-media-server-2022/) *(Update Pending)*

#### 🌐 Web Server
- [WordPress on Docker with Nginx, Traefik, LE SSL, Security, and Speed](https://www.simplehomelab.com/wordpress-on-docker-traefik/) *(Update Pending)*

#### 🤖 Automation
- [Deployrr: Automate Docker Compose based Homelab Setup](https://www.simplehomelab.com/deployrr/) [📹](https://youtu.be/OnoKy73b-w4)

---

## 🚀 Featured Applications

**150+ Docker applications** ready for deployment, sourced from the [Deployrr Repository](https://github.com/SimpleHomelab/Deployrr/blob/main/APPS.md):

### 📱 Media & Entertainment
**Adminer**, **Airsonic-Advanced**, **Audiobookshelf**, **Bazarr**, **Beets**, **Calibre**, **Calibre-Web**, **Emby**, **Funkwhale**, **GameVault**, **Immich**, **Jellyfin**, **Jellyseerr**, **Kavita**, **Kometa**, **Komga**, **Lidarr**, **Mylar3**, **Navidrome**, **Ombi**, **Overseerr**, **Plex**, **Radarr**, **Sonarr**, **Tautulli**, **Trilium Next**

### 🏠 Home Automation & IoT
**ESPHome**, **Home Assistant Core**, **Homebridge**, **Mosquitto**, **MQTTX Web**, **Node-RED**, **OpenHands**

### 🔧 Development & Productivity
**Authentik**, **Authelia**, **Bookstack**, **CyberChef**, **DokuWiki**, **Flowise**, **FreshRSS**, **Grocy**, **Guacamole**, **IT-Tools**, **Nextcloud**, **n8n**, **Ollama**, **Open-WebUI**, **Paperless-AI**, **Paperless-NGX**, **PdfDing**, **Privatebin**, **Stirling PDF**, **Visual Studio Code Server**, **Vikunja**, **WikiDocs**

### 📊 Monitoring & Analytics
**cAdvisor**, **Change Detection**, **Dockwatch**, **Dozzle**, **Dozzle Agent**, **Glances**, **Grafana**, **InfluxDB**, **Netdata**, **Node Exporter**, **Prometheus**, **Scrutiny**, **Smokeping**, **Speedtest-Tracker**, **Uptime-Kuma**, **Watchtower**, **What's Up Docker (WUD)**

### 🌐 Networking & Security
**Cloudflare Tunnel**, **CrowdSec**, **CrowdSec Firewall Bouncer**, **Gluetun**, **Pi-hole**, **Tailscale**, **Traefik**, **Traefik Access Logs**, **Traefik Bouncer**, **Traefik Certs Dumper**, **Traefik Error Logs**, **WG-Easy**, **Wireguard**, **ZeroTier**

### 🎨 Dashboards & Organization
**Dashy**, **Flame**, **Heimdall**, **Homarr**, **Homer**, **Homepage**, **Organizr**, **Theme Park**

### 💾 Storage & Backup
**Resilio Sync**, **Vaultwarden**

### 🗄️ Databases & Data
**Baikal**, **MariaDB**, **PostgreSQL**, **PgAdmin**, **phpMyAdmin**, **Qdrant**, **Redis**, **Redis Commander**, **Weaviate**

### 🎯 Utilities & Tools
**Chromium**, **Cleanuparr**, **Cloud Commander**, **DDNS Updater**, **DeUnhealth**, **DigiKam**, **Docker Garbage Collection**, **Double Commander**, **DweebUI**, **FileZilla**, **Flaresolverr**, **Gotenberg**, **GPTWOL**, **Huntarr**, **Jackett**, **Kasm**, **Lollypop**, **Maintainerr**, **Notifiarr**, **OAuth**, **Piwigo**, **Portainer**, **Prowlarr**, **qBittorrent**, **qBittorrent with VPN**, **Remmina**, **SABnzbd**, **SearXNG**, **ShellInABox**, **Socket Proxy**, **SSHwifty**, **Tika**, **TinyAuth**, **Transmission**, **Wallos**

---

## ⚡ Quick Start Commands

### 🎯 Essential Docker Aliases

I use **Bash Aliases** installed via Deployrr for streamlined Docker management:

| Command | Description |
|---------|-------------|
| `dcup` | Start Docker stack |
| `dcdown` | Stop Docker stack |
| `dcrec` | Start or recreate specific service/full stack |
| `dcstop` | Stop specific service/full stack |
| `dcrestart` | Restart specific service/full stack |
| `dclogs` | View real-time logs for stack/service |
| `dcpull` | Pull new images for stack/service |

> 📖 **Learn More**: [Essential Docker Commands & Time-Saving Aliases](https://www.simplehomelab.com/udms-13-docker-and-docker-compose-commands/) | [Bash Aliases in Deployrr](https://docs.deployrr.app/operating-system/bash-aliases-explained)

---

## 🤝 Support & Community

**Documenting, writing guides, and maintaining this repository** requires hundreds of hours of dedicated work. Your support helps keep this project alive and continuously updated.

### 🎖️ Join the Geek Army
<div style="text-align:center;margin:20px">
<a href="https://www.simplehomelab.com/geek-army/join/" target="_blank" rel="nofollow noopener noreferrer">
<img src="https://www.simplehomelab.com/images/2024/01/become-a-member.png" alt="Join the Geek Army" width="258" height="76" />
</a>
</div>

### 💬 Join the Discord Community
<div style="text-align:center;margin:20px">
<a href="https://www.simplehomelab.com/discord-github/" target="_blank" rel="nofollow noopener noreferrer">
<img src="https://www.simplehomelab.com/images/2022/05/join-discord-300x75.png" alt="Join Discord" width="300" height="75" />
</a>
</div>

---

## 📝 License & Attribution

This repository contains real-world Docker configurations based on:
- [Deployrr](https://www.simplehomelab.com/deployrr/) automation platform
- [Ultimate Docker Media Server](https://www.simplehomelab.com/ultimate-docker-media-server-udms-01/) series
- [SimpleHomelab.com](https://www.simplehomelab.com/) community resources

**Created by**: Anand from [SimpleHomelab.com](https://www.simplehomelab.com/) (formerly SmartHomeBeginner.com)