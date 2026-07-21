# Project Journal

This journal documents the major milestones, decisions, and progress made while building my homelab. While the technical documentation throughout this repository explains *how* each component was deployed, this journal provides a chronological record of the project's evolution, challenges, and accomplishments.

---

# 2026-07-20

## Milestone: Internet Upgrade

### Summary

Upgraded the home internet connection to Spectrum Gig service to provide the bandwidth required for virtualization, remote administration, software downloads, and future self-hosted services.

### Connection Test

| Download | Upload | Ping |
|----------:|--------:|-----:|
| 896 Mbps | 39 Mbps | 18 ms |

### Why This Matters

A reliable, high-speed internet connection is an important foundation for a homelab. It enables remote management, software updates, container image downloads, and future public-facing services.

### Next Steps

- Install Proxmox VE
- Configure the managed switch
- Begin building the RackMate T2

---

# 2026-07-20

## Milestone: Hardware Acquisition

### TP-Link TL-SG108E Managed Switch

Purchased the TP-Link TL-SG108E Easy Smart Managed Switch to begin building the physical network infrastructure for the homelab.

### Why This Hardware

The switch was selected because it provides:

- Gigabit Ethernet
- Managed switching
- VLAN support
- Port mirroring
- QoS capabilities
- Fanless operation
- Excellent value for learning enterprise networking concepts

### Goal

The managed switch will replace a basic flat network with one capable of supporting future VLANs, monitoring, and network segmentation.

### Next Steps

Receive the switch and integrate it into the network.

---

# 2026-07-21

## Milestone: TP-Link Switch Received

### Summary

Received the TP-Link TL-SG108E managed switch.

This marks the beginning of building the physical networking infrastructure for the homelab. Until this point, networking relied solely on the ISP-provided router. The addition of a managed switch provides the foundation for learning enterprise networking concepts and expanding the lab beyond basic connectivity.

### Current Lab Status

- Proxmox VE installed
- Ubuntu Docker VM created
- DHCP reservation configured
- TP-Link managed switch received

### Next Steps

Configure the switch and integrate it into the existing network.

---

# 2026-07-21

## Milestone: Docker Deployment

### Summary

Completed the Docker installation milestone on the Ubuntu Server virtual machine (`docker-01`).

This establishes the foundation for hosting containerized services throughout the homelab. Future applications—including Portainer, Jellyfin, Sonarr, Radarr, Prowlarr, Bazarr, monitoring tools, and other self-hosted services—will be deployed from this Docker host.

### Work Completed

- Updated Ubuntu package repositories
- Removed legacy Docker packages
- Installed required prerequisite packages
- Added Docker's official APT repository
- Installed Docker Engine
- Installed Docker Compose
- Verified Docker installation
- Verified the Docker service was running
- Successfully executed the Hello World test container

### Result

Docker is fully operational and ready to host production container workloads within the homelab.

### Lessons Learned

- Installing Docker from Docker's official repository ensures access to the latest stable releases.
- Verifying the Docker service and running the Hello World container provides confidence that the installation is functioning correctly before deploying additional services.
- Documenting each milestone immediately after completion keeps the project organized and reproducible.

### Next Steps

Deploy Portainer to provide centralized management of Docker containers through a web-based interface.