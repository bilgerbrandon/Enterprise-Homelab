# Docker Host Virtual Machine

## Objective

Deploy a dedicated Ubuntu Server virtual machine that will host all Docker containers for the homelab.

---

# Virtual Machine Information

VM ID

100

Hostname

docker-01

Purpose

Docker Host

Operating System

Ubuntu Server LTS

---

# Configuration

BIOS

- OVMF (UEFI)

Machine

- q35

Network Adapter

- VirtIO

Guest Agent

- Enabled

---

# Why a Dedicated Docker VM?

Running Docker inside its own virtual machine provides several advantages:

- Isolation from the Proxmox host
- Easier backups
- Easier disaster recovery
- Simple migration to another Proxmox node
- Ability to snapshot before major upgrades

---

# Validation

Verified:

- Ubuntu installed successfully
- Internet connectivity working
- VM boots normally
- Console access available
- SSH available

---

# Lessons Learned

Separating infrastructure services from the hypervisor follows virtualization best practices and reduces operational risk.

---

# Next Steps

- Install Docker Engine
- Install Docker Compose
- Install Portainer