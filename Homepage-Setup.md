# Homepage Setup

## Overview

Homepage is a lightweight, self-hosted dashboard that provides a centralized landing page for services running within the Enterprise Homelab. It allows quick access to infrastructure, media services, monitoring tools, and other self-hosted applications through a clean web interface.

Homepage will serve as the primary dashboard for navigating the homelab as additional services are deployed.

---

# Objectives

- Deploy Homepage using Docker
- Manage the deployment with Portainer
- Configure persistent application storage
- Customize the dashboard
- Create the first infrastructure service tile

---

# Prerequisites

The following components were completed before beginning this deployment:

- Ubuntu Server installed
- Docker Engine installed
- Portainer configured
- Local Docker environment connected

---

# Creating the Configuration Directory

A persistent configuration directory was created on the host system.

```bash
mkdir -p /home/brandon/docker/homepage/config
```

Using a bind mount allows Homepage configuration files to remain on the host, making backups and future customization significantly easier.

---

# Deploying Homepage

Homepage was deployed using a Docker Stack inside Portainer.

```yaml
services:
  homepage:
    image: ghcr.io/gethomepage/homepage:latest
    container_name: homepage
    restart: unless-stopped
    ports:
      - "3000:3000"
    environment:
      HOMEPAGE_ALLOWED_HOSTS: "*"
      PUID: "1000"
      PGID: "1000"
    volumes:
      - /home/brandon/docker/homepage/config:/app/config
```

Deploying with a Docker Stack simplifies future updates and aligns with Docker Compose best practices.

---

# Verifying Deployment

After deployment, Homepage became accessible at:

```
http://192.168.1.243:3000
```

The container successfully started and presented the default Homepage dashboard.

Screenshot:

```
Photos/10-homepage-default-dashboard.png
```

---

# Initial Dashboard Configuration

Homepage ships with several example groups and bookmarks intended for demonstration purposes.

The default examples were removed and replaced with infrastructure relevant to the Enterprise Homelab.

The first service added was Portainer.

Example configuration:

```yaml
- Infrastructure:
    - Portainer:
        href: https://192.168.1.243:9443
        description: Docker Management
        icon: portainer.png
```

After refreshing the Homepage interface, the Portainer tile appeared under the Infrastructure section.

Screenshot:

```
Photos/11-homepage-portainer-tile.png
```

---

# Lessons Learned

This deployment introduced several important concepts:

- Docker Stacks simplify application deployment.
- Bind mounts keep configuration separate from containers.
- YAML configuration files control Homepage layout and services.
- Homepage automatically reloads configuration changes after refreshing the browser.
- Building the dashboard incrementally keeps configuration organized as the homelab grows.

---

# Outcome

Homepage is now operational and serves as the central dashboard for the Enterprise Homelab.

Current dashboard:

- Infrastructure
  - Portainer

Additional services will be added as the homelab expands.

---

# Future Dashboard Layout

Planned categories include:

## Infrastructure

- Homepage
- Portainer
- Proxmox
- Tailscale

## Media

- Jellyfin
- Sonarr
- Radarr
- Prowlarr
- Bazarr

## Monitoring

- Dozzle
- Grafana
- Prometheus

## Network

- Nginx Proxy Manager

---

# Next Steps

The next milestone is deploying Dozzle to provide real-time Docker container log monitoring.

After Dozzle, monitoring and management capabilities will continue expanding alongside additional self-hosted services.