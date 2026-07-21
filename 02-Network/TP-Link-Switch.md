# TP-Link TL-SG108E Easy Smart Switch

## Objective

Add a managed Gigabit Ethernet switch to the homelab to provide network expansion and introduce Layer 2 management features such as VLANs, QoS, port mirroring, and traffic monitoring.

---

# Overview

Model

- TP-Link TL-SG108E

Product Type

- Easy Smart Switch

Ports

- 8 × 10/100/1000 Mbps RJ45

Management

- Web Interface

Construction

- Metal Housing

Power

- External 5V Power Adapter

Warranty

- 3 Years

---

# Why This Switch?

The TP-Link TL-SG108E was selected because it provides enterprise-style management features while remaining affordable and simple enough for a learning environment.

Key features include:

- Gigabit Ethernet on all ports
- IEEE 802.1Q VLAN support
- Port Mirroring
- QoS
- Loop Prevention
- Broadcast Storm Control
- IGMP Snooping
- Cable Diagnostics
- Port Statistics

Although this switch is not a fully managed enterprise switch, it offers enough functionality to learn networking concepts that are directly applicable to larger enterprise environments.

---

# Planned Role

This switch will become the central network distribution switch for the homelab.

Initially it will connect:

- Internet Router
- Proxmox Host
- MacBook
- Future NAS
- Future Wireless Access Point

As the lab grows, additional devices and virtual infrastructure will be connected through this switch.

---

# First Impressions

The switch arrived well packaged with protective foam and an anti-static bag.

Notable observations:

- Metal chassis
- Compact footprint
- Fanless design
- Clearly labeled ports
- Solid build quality

The fanless design makes it suitable for use in a home office without introducing additional noise.

---

# Lessons Learned

Moving from an unmanaged switch to a managed switch opens the door to learning many enterprise networking concepts including VLAN segmentation, monitoring, and traffic optimization.

This switch represents the first dedicated networking component purchased specifically for the homelab.

---

# Next Steps

- Power on the switch
- Upgrade firmware if necessary
- Configure management IP
- Change the administrator password
- Rename the switch
- Back up the configuration
- Begin planning VLAN implementation

## Configuration Backup

After completing the initial switch configuration, a backup of the running configuration was created using the built-in Backup & Restore utility.

The backup is stored locally and is not included in this repository because it is a binary configuration file intended only for disaster recovery.