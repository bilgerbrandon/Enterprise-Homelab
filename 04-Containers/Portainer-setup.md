# Portainer Setup

## Overview

Portainer Community Edition was deployed to provide a centralized web-based interface for managing Docker containers, images, networks, volumes, and application stacks. While Docker can be managed entirely from the command line, Portainer simplifies administration by providing a graphical interface that improves visibility and reduces operational complexity.

This installation serves as the primary container management platform for the Enterprise Homelab and will be used to deploy and manage future services including Jellyfin, Sonarr, Radarr, Prowlarr, Bazarr, Homepage, and other self-hosted applications.

---

# Objectives

- Deploy Portainer Community Edition
- Configure persistent application storage
- Connect the local Docker environment
- Verify communication with the Docker Engine
- Prepare the server for future container deployments

---

# Prerequisites

The following components were completed before beginning this installation:

- Ubuntu Server installed
- System fully updated
- Docker Engine installed
- Docker service enabled
- Current user added to the Docker group
- Docker functionality verified using the Hello World container

---

# Creating the Persistent Volume

A Docker volume was created to store Portainer configuration data outside of the container.

```bash
docker volume create portainer_data
```

Using a persistent volume ensures that Portainer configuration and user data remain intact even if the container is removed or recreated.

---

# Deploying Portainer

Portainer was deployed using the official Long-Term Support (LTS) container image.

```bash
docker run -d \
  --name portainer \
  --restart unless-stopped \
  -p 8000:8000 \
  -p 9443:9443 \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  portainer/portainer-ce:lts
```

### Container Configuration

| Option | Purpose |
|---------|----------|
| `--restart unless-stopped` | Automatically restarts Portainer after reboot |
| `-p 9443:9443` | Secure HTTPS web interface |
| `-p 8000:8000` | Edge Agent communication |
| Docker Socket | Allows Portainer to communicate with Docker |
| Persistent Volume | Stores Portainer configuration |

---

# Verifying Deployment

Container status was verified using:

```bash
docker ps
```

The Portainer container successfully entered the **Up** state and exposed the expected ports.

Screenshot:

```
Photos/07-portainer-container-running.png
```

---

# Initial Configuration

Portainer was accessed using HTTPS.

```
https://<SERVER-IP>:9443
```

During first-time setup:

- Administrator account created
- Strong password configured
- Local Docker environment detected
- Local environment connected

Unlike many older tutorials, Portainer Community Edition 2.39 LTS requires a **one-time setup token** during the initial administrator creation process.

The setup token was retrieved from the container logs using:

```bash
docker logs portainer
```

This token is generated during initial startup and must be entered before the administrator account can be created.

---

# Environment Verification

After completing setup, Portainer successfully connected to the local Docker Engine.

Verified resources included:

- Docker Containers
- Images
- Volumes
- CPU Information
- Memory Information

Screenshots:

```
Photos/08-portainer-dashboard.png

Photos/09-portainer-local-environment.png
```

---

# Troubleshooting

## Docker Permission Denied

Initially Docker required `sudo`.

Resolved by adding the current user to the Docker group:

```bash
sudo usermod -aG docker $USER
newgrp docker
```

---

## Existing Container Conflict

Attempting to deploy Portainer a second time produced:

```
Conflict. The container name "/portainer" is already in use
```

The issue was caused by an existing running Portainer container.

Container status was verified using:

```bash
docker ps -a
```

---

## Initial Setup Timeout

Portainer temporarily locked the administrator setup after the initial setup window expired.

Resolved by restarting the container:

```bash
docker restart portainer
```

---

## Invalid Setup Token

The initial administrator setup rejected an invalid setup token.

The correct token was retrieved directly from the Portainer container logs before completing the setup.

---

# Lessons Learned

This deployment reinforced several important Docker administration concepts:

- Containers should use persistent volumes whenever application data must survive recreation.
- Docker socket mounting allows Portainer to manage the local Docker host.
- Docker groups eliminate the need for repeated use of `sudo`.
- Portainer Community Edition now includes additional security protections during initial deployment through the use of one-time setup tokens.
- Reading container logs is an essential troubleshooting skill when deploying self-hosted applications.

---

# Outcome

Portainer is now fully operational and serves as the primary management interface for the Enterprise Homelab Docker environment.

Current status:

- Ubuntu Server operational
- Docker Engine installed
- Portainer configured
- Local Docker environment connected
- Ready for containerized service deployment

---

# Next Steps

The next phase of the project will focus on deploying production-ready Docker services using Portainer.

Planned deployments include:

- Homepage
- Dozzle
- Watchtower
- Jellyfin
- Sonarr
- Radarr
- Prowlarr
- Bazarr
- Tailscale
- Nginx Proxy Manager
- Monitoring stack (Grafana and Prometheus)