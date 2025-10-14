# Description

This repo contains my (Anand from [SimpleHomelab.com](https://www.simplehomelab.com/); previously SmartHomeBeginner.com) actual Docker-based server setups. 

Unlike my previous setups/guides, my current setup is based on [Deployrr](https://www.simplehomelab.com/deployrr/) and [Ultimate Docker Media Server](https://www.simplehomelab.com/ultimate-docker-media-server-udms-01/)(UDMS) series, based on templates available in [Deplorr repository](https://github.com/SimpleHomelab/Deployrr). 

The purpose of this repository is to 1) share my actual setup and 2) provide examples or ways too do more than what is done by Deployrr or discussed in UDMS series. 

ADD SOCIAL MEDIA PROFILES

## My Hardware

I believe in keeping my homelab simple and energy efficient.

<ul>
<li>TopTon V700 Mini PC with Intel 13th Gen “Raptor Lake” i7-13800H, 64 GB RAM, 2x2TB NVMe M.2 ZFS Raid Mirror for Proxmox Virtual Environment and 4 TB SATA III SSD storage.</li>
<li>Synology DS918+ with DX517 Expansion Unit and 8 GB RAM used mainly for storage.</li>
<li>Oracle Ampere A1 ARM based VPS with 4 vCPU and 24 GB RAM for Web Server.</li>
<li>

My home network is powered by OPNsense running as a Proxmox VM. All hosts are networked using Tailscale. 

## My Docker Hosts

Docker setup files (e.g. Docker Compose) from the following Docker Hosts are pooled and pushed to this repo. 

### Home Server
<ul>
<li>Ubuntu 24.04 on Proxmox Unprivileged LXC.</li>
<li>8 vCPU, 8 GB RAM, 4 GB Swap, 64 GB OS disk, 32 GB disk for Docker data.</li>
<li>Built with Deployrr and some custom apps.</li>
<li>Any file/folder in this repo belonging to my home server will have the prefix/suffix of <strong>hs</strong> in the name.</li>
</ul>

### Media Database Server
<ul>
<li>Ubuntu 24.04 on Proxmox Unprivileged LXC.</li>
<li>12 vCPU, 12 GB RAM, 4 GB Swap, 64 GB OS disk, 72 GB disk for Docker data.</li>
<li>Built with Deployrr and some custom apps.</li>
<li>Any file/folder in this repo belonging to my media database server will have the prefix/suffix of <strong>mds</strong> in the name.</li>
</ul>

### Web Server
<ul>
<li>Ubuntu 24.04 arm64 on Oracle Ampere A1.</li>
<li>4 vCPU, 24 GB RAM, 100 GB OS disk, and 100 GB storage disk.</li>
<li>Built with Deployrr and some custom apps.</li>
<li>Any file/folder in this repo belonging to my web server will have the prefix/suffix of <strong>ws-arm</strong> in the name.</li>
</ul>

### Synology DS918+ and DX517 Expansion Unit
<ul>
<li>DSM 7.2.</li>
<li>8 GB RAM, Volume 1 on main unit: 4x18 TB in SHR2, Volume 2 on Expansion Unit: 4x18 TB in SHR2.</li>
<li>At this point this setup still follows the standards from my older guides.</li>
<li>Any file/folder in this repo belonging to my Synology setup will have the prefix/suffix of <strong>ds918</strong> in the name.</li>
</ul>

### Archives
Files and folders inside _archives_ are not actively maintained. But they may still provide a good starting point. 

# Guides and Videos

## Ultimate Docker Media Server Series:

<ol>
    <li><a href="https://www.simplehomelab.com/udms-01-introduction-and-overview/">Introduction and Overview</a></li>
    <li><a href="https://www.simplehomelab.com/udms-02-hardware-nas-minipc-vps/">Hardware: NAS, Mini PC, or VPS (FREE!). Which one?</a></li>
    <li><a href="https://www.simplehomelab.com/udms-03-best-home-server-os/">Best Home Server OS, Proxmox LXC vs VM</a></li>
    <li><a href="https://www.simplehomelab.com/udms-04-install-proxmox-on-mini-pc/">Install Proxmox on Mini PC with ZFS RAID1 Mirror + 3 Tweaks</a> [<a href="https://youtu.be/2nIPY7D-UA0" target="_blank">Video</a>]</li>
    <li><a href="https://www.simplehomelab.com/udms-05-installing-ubuntu-on-proxmox/">Installing and Prepping Ubuntu/Debian</a> [<a href="https://youtu.be/-ZSQdJ62r-Q" target="_blank">Video</a>]</li>
    <li>Mounting Remote Folders using Rclone [<a href="https://youtu.be/D-XS0biLP14" target="_blank">Video</a>]</li>
    <li>Mounting Remote Folders using SMB/CIFS (Coming Soon)</li>
    <li>Mounting Remote Folders using NFS (Coming Soon)</li>
    <li>Binding Mounting on Proxmox Unpriviled LXC (Coming Soon)</li>
    <li><a href="https://www.simplehomelab.com/udms-10-proxmox-lxc-network-device-passthrough/">Proxmox Unprivileged LXC Network Node Passthrough</a> [<a href="https://youtu.be/r0nGMFs5pCY" target="_blank">Video</a>]</li>
    <li><a href="https://www.simplehomelab.com/udms-11-gpu-passthrough-on-proxmox-lxc/">Proxmox Unprivileged LXC iGPU Node Passthrough</a> [<a href="https://youtu.be/kvnJYyyLoIk" target="_blank">Video</a>]</li>
    <li><a href="https://www.simplehomelab.com/udms-12-install-docker-and-docker-compose/">Installing Docker and Docker Compose on Ubuntu/Debian</a></li>
    <li><a href="https://www.simplehomelab.com/udms-13-docker-and-docker-compose-commands/">Essential Docker Commands & Time-Saving Aliases</a></li>
    <li><a href="https://www.simplehomelab.com/udms-14-docker-media-server/">Kickass Docker Media Server with 150+ Apps</a> [<a href="https://youtu.be/THuLgGwq0vg" target="_blank">Video</a>]</li>
    <li>Best Docker Containers for Homelab (Coming Soon)</li>
    <li><a href="https://www.simplehomelab.com/udms-part-16-tailscale-homelab-remote-access/">Exposing Apps to the Internet: Tailscale</a> [<a href="https://youtu.be/M6GMp4FJrB8" target="_blank">Video</a>]</li>
    <li>Exposing Apps to the Internet: Nginx Proxy Manager (Coming Soon)</li>
    <li><a href="https://www.simplehomelab.com/udms-18-traefik-docker-compose-guide/">Exposing Apps to the Internet: Traefik Reverse Proxy</a> [<a href="https://www.youtube.com/playlist?list=PL1Hno7tIbSWUGrZSqeB9aCsdAuoeVwvgh" target="_blank">Video 1</a>]</li>
    <li><a href="https://www.simplehomelab.com/udms-19-authelia-docker-compose/">Authentication for Docker Apps - Authelia</a> [<a href="https://youtu.be/UIq8PLZHBtk" target="_blank">Video</a>]</li>
    <li>Authentication for Docker Apps - Google OAuth 2 [<a href="https://youtu.be/SCKALXprTQE" target="_blank">Video</a>]</li>
    <li>Authentication for Docker Apps - Authentik [<a href="https://youtu.be/GoUmJAe1MKc" target="_blank">Video</a>]</li>
    <li><a href="https://www.simplehomelab.com/udms-22-crowdsec-docker-compose/">CrowdSec Docker Compose – Bulletproof IPS for Homelabs</a></li>
    <li><a href="https://www.simplehomelab.com/udms-23-crowdsec-cloudflare-bouncer/">Setting up Crowdsec Cloudflare Bouncer</a></li>
    <li><a href="https://www.simplehomelab.com/udms-24-crowdsec-traefik-bouncer/">Setting up Crowdsec Traefik Bouncer</a></li>
    <li>Advanced Topics: Traefik Plugins (Coming Soon)</li>
    <li>Advanced Topics: Traefik Multiple Domains (Coming Soon)</li>
    <li>Advanced Topics: Traefik Domain Passthrough (Coming Soon)</li>
    <li>Advanced Topics: <a href="https://www.simplehomelab.com/udms-28-traefik-auth-bypass/">Traefik Conditional Auth Bypass</a></li>
    <li>Advanced Topics: <a href="https://www.simplehomelab.com/udms-29-crowdsec-multiserver/">CrowdSec Multiserver Setup</a></li>
    <li>Closing Thoughts and Options to Level Up (Coming Soon)</li>
</ol>

## Synology:
- [Ultimate Synology NAS Docker Compose Media Server 2022](https://www.simplehomelab.com/synology-nas-docker-media-server-2022/) - UPDATE PENDING

## Web Server:
- [WordPress on Docker with Nginx, Traefik, LE SSL, Security, and Speed](https://www.simplehomelab.com/wordpress-on-docker-traefik/) - UPDATE PENDING

## Automate the Process:
- [Deployrr: Automate Docker Compose based Homelab Setup](https://www.simplehomelab.com/deployrr/) [VIDEO](https://youtu.be/OnoKy73b-w4)

# Apps in this Repo

Majority of the apps in my setup come directly from the [Deployrr Repository](https://github.com/SimpleHomelab/Deployrr/blob/main/APPS.md), which supports nearly 150 apps as listed below. I do not use all of them in setup but do have some that are not installed natively by Deployrr. 

Adminer, Airsonic-Advanced, Authentik, Audiobookshelf, Authelia, Baikal, Bazarr, Beets, Bookstack, cAdvisor, Calibre, Calibre-Web, Change Detection, Chromium, Cleanuparr, Cloud Commander, Cloudflare Tunnel, CrowdSec, CrowdSec Firewall Bouncer, CyberChef, Dashy, DDNS Updater, DeUnhealth, DigiKam, Dockwatch, Docker Garbage Collection, DokuWiki, Double Commander, Dozzle, Dozzle Agent, DweebUI, Emby, ESPHome, FileZilla, Flame, Flaresolverr, Flowise, FreshRSS, Funkwhale, GameVault, Glances, Gluetun, Gonic, Gotenberg, GPTWOL, Grafana, Grocy, Guacamole, Heimdall, Homarr, Home Assistant Core, Homebridge, Homer, Homepage, Huntarr, Immich, InfluxDB, IT-Tools, Jackett, Jellyfin, Jellyseerr, Kasm, Kavita, Kometa, Komga, Lidarr, Lollypop, Maintainerr, MariaDB, Mosquitto, MQTTX Web, Mylar3, n8n, Navidrome, Netdata, Nextcloud, Node Exporter, Node-RED, Notifiarr, OAuth, Ollama, Ombi, OpenHands, Open-WebUI, Organizr, Overseerr, Paperless-AI, Paperless-NGX, PdfDing, PgAdmin, phpMyAdmin, Pi-hole, Piwigo, Plex, Portainer, PostgreSQL, Privatebin, Prometheus, Prowlarr, qBittorrent, qBittorrent with VPN, Qdrant, Radarr, Redis, Redis Commander, Remmina, Resilio Sync, SABnzbd, Scrutiny, SearXNG, ShellInABox, Smokeping, Socket Proxy, Sonarr, Speedtest-Tracker, SSHwifty, Stirling PDF, Tailscale, Tautulli, The Lounge, Theme Park, Tika, TinyAuth, Traefik, Traefik Access Logs, Traefik Bouncer, Traefik Certs Dumper, Traefik Error Logs, Transmission, Trilium Next, Uptime-Kuma, Vaultwarden, Vikunja, Visual Studio Code Server, Wallos, Watchtower, Weaviate, WG-Easy, What's Up Docker (WUD), WikiDocs, Wireguard, and ZeroTier

## Bash Aliases 

I use Bash Aliases installed via Deployrr to simplify managing my Docker stacks. But you may also install it manually using my UDMS guide: [Essential Docker Commands & Time-Saving Aliases](https://www.simplehomelab.com/udms-13-docker-and-docker-compose-commands/).

Here are some example alias commands:

- `dcup` - Start Docker stack
- `dcdown` - Stop Docker stack
- `dcrec` - Start or recreate a specific service or the full stack
- `dcstop` - Stop a specific service or the full stack
- `dcrestart` - Restart a specific service or the full stack
- `dclogs` - See real-time logs for the corresponding stack or service
- `dcpull` - Pull new images for the corresponding stack or service

A full list of supported Bash Aliases are described in Deployrr Docs: [Bash Aliases in Deployrr](https://docs.deployrr.app/operating-system/bash-aliases-explained).

# Support My Work

Documenting, writing guides, and keeping this repo update-to-date takes hundreds of hours of work. Please consider supporting my work to show your appreciation. 

## Join the Geek Amry

<div style="text-align:center;margin:20px"><a href="https://www.simplehomelab.com/geek-army/join/" target="_blank" rel="nofollow noopener noreferrer"><img src="https://www.simplehomelab.com/images/2024/01/become-a-member.png" alt="" width="258" height="76" /></a></div>

## Join the Discord Community

<div style="text-align:center;margin:20px"><a href="https://www.simplehomelab.com/discord-github/" target="_blank" rel="nofollow noopener noreferrer"><img src="https://www.simplehomelab.com/images/2022/05/join-discord-300x75.png" alt="" width="300" height="75" /></a></div>