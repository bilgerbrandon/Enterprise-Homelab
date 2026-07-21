# Brandon's Enterprise Homelab

A hands-on homelab project focused on virtualization, networking, containerization, self-hosting, monitoring, and infrastructure documentation.

This repository documents the complete build process, including hardware selection, system configuration, troubleshooting, verification, screenshots, lessons learned, and project milestones.

---

## Project Goals

The purpose of this homelab is to:

- Build practical experience with enterprise IT infrastructure
- Learn Proxmox virtualization and virtual machine management
- Develop networking skills using managed switches, VLANs, DHCP, DNS, and firewalling
- Deploy and manage containerized services with Docker and Docker Compose
- Build a self-hosted media and services environment
- Implement monitoring, backups, documentation, and troubleshooting procedures
- Create a professional technical portfolio that demonstrates real-world IT skills

---

## Current Architecture

```text
Internet
   │
Spectrum Router
   │
TP-Link TL-SG108E Managed Switch
   │
   ├── Proxmox Host
   │      └── docker-01
   │             └── Docker Engine
   │
   ├── Future Proxmox Nodes
   ├── Storage
   └── Client Devices
```

A detailed network diagram will be added as the environment expands.

---

## Current Environment

| Component | Role | Status |
|---|---|---|
| Spectrum Gig Internet | Internet connectivity | Complete |
| TP-Link TL-SG108E | Managed network switch | In progress |
| Datto appliance | Primary Proxmox host | Complete |
| Proxmox VE | Virtualization platform | Complete |
| `docker-01` | Ubuntu Server Docker host | Complete |
| Docker Engine | Container runtime | Complete |
| Docker Compose | Multi-container deployment | Complete |
| Portainer | Docker management interface | Planned |
| Media stack | Self-hosted media services | Planned |
| Monitoring platform | Infrastructure monitoring | Planned |

---

## Completed Milestones

### Virtualization

- Installed Proxmox VE on the primary host
- Created an Ubuntu Server virtual machine
- Installed and verified the QEMU Guest Agent
- Configured a DHCP reservation
- Renamed the Docker host VM to `docker-01`

### Networking

- Upgraded to Spectrum Gig Internet
- Purchased a TP-Link TL-SG108E managed switch
- Began documenting the network architecture and IP addressing plan

### Containers

- Prepared Ubuntu Server for Docker
- Added Docker's official APT repository
- Installed Docker Engine
- Installed Docker Compose
- Verified the Docker service
- Successfully ran the Docker Hello World container

---

## Planned Services

The lab is being built to support services such as:

- Portainer
- Jellyfin
- Sonarr
- Radarr
- Prowlarr
- Bazarr
- Homepage dashboard
- Network monitoring
- System monitoring
- Centralized logging
- Backup services
- DNS filtering
- File sharing and storage

Media-stack deployments will follow established best practices, including guidance from TRaSH Guides where applicable.

---

## Repository Structure

```text
Enterprise-Homelab/
├── 01-Hardware/
├── 02-Network/
├── 03-Proxmox/
├── 04-Containers/
├── 05-Media-Stack/
├── 06-Services/
├── 07-Monitoring/
├── 08-Learning/
├── CHANGELOG.md
├── Project-Journal.md
└── README.md
```

| Section | Purpose |
|---|---|
| `01-Hardware` | Hardware inventory, specifications, purchases, and rack documentation |
| `02-Network` | Network design, addressing, switching, VLANs, and firewall documentation |
| `03-Proxmox` | Proxmox installation, configuration, virtual machines, and clustering |
| `04-Containers` | Ubuntu preparation, Docker, Docker Compose, and Portainer |
| `05-Media-Stack` | Jellyfin and supporting media-management applications |
| `06-Services` | Additional self-hosted applications and infrastructure services |
| `07-Monitoring` | Monitoring, logging, alerting, and performance visibility |
| `08-Learning` | Technical notes, labs, troubleshooting exercises, and lessons learned |

---

## Documentation Workflow

Each major milestone follows the same process:

```text
Build
  ↓
Verify
  ↓
Capture Screenshots
  ↓
Write Documentation
  ↓
Commit to Git
  ↓
Continue to Next Milestone
```

Documentation typically includes:

- Objective
- Environment
- Commands or configuration steps
- Verification
- Screenshots
- Troubleshooting notes
- Lessons learned
- Next steps

---

## Skills Demonstrated

This project demonstrates practical experience with:

- Linux server administration
- Proxmox VE
- Virtual machines
- Docker
- Docker Compose
- Managed Ethernet switching
- DHCP and IP addressing
- VLAN planning
- Service verification
- Technical troubleshooting
- Git and GitHub
- Infrastructure documentation
- Change tracking
- Project planning

---

## Project Status

The homelab is actively being developed.

The current focus is completing the container-management foundation by deploying Portainer. Future phases will include Docker Compose standards, monitoring, network segmentation, additional Proxmox nodes, and the self-hosted media stack.

See [`Project-Journal.md`](Project-Journal.md) for chronological progress and [`CHANGELOG.md`](CHANGELOG.md) for repository updates.

---

## Author

**Brandon Bilger**

Aspiring IT professional building practical experience in networking, virtualization, Linux administration, containerization, and self-hosted infrastructure.