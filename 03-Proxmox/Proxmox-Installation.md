# Proxmox VE Installation

## Objective

Install Proxmox VE on the Datto N Series to serve as the primary virtualization platform for the homelab.

---

# Hardware

Host

- Datto N Series
- Intel Core i5-12500T
- 16 GB DDR5 Memory

Storage

- SK hynix PC801 2TB NVMe SSD

Networking

- Connected to the home network through the primary router
- Future managed switch integration planned

---

# Installation Summary

Operating System

- Proxmox VE

Installation Media

- Bootable USB created with Balena Etcher

Installation Type

- Default ext4 filesystem

---

# Installation Steps

- Downloaded the latest Proxmox VE ISO.
- Created a bootable USB installer.
- Booted the Datto from the USB drive.
- Installed Proxmox on the 2TB NVMe SSD.
- Configured hostname, administrator password, and networking.
- Completed the installation and rebooted into Proxmox.

---

# Verification

Successfully logged into the Proxmox web interface.

```
https://<server-ip>:8006
```

Verified:

- Datacenter created
- Node online
- Local storage available
- VM storage available

---

# Lessons Learned

Installing Proxmox directly on bare metal provides a lightweight and enterprise-grade virtualization platform capable of hosting multiple virtual machines with minimal overhead.

---

# Next Steps

- Configure Proxmox
- Create the Docker Host virtual machine