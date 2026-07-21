# QEMU Guest Agent

## Objective

Install and enable the QEMU Guest Agent to improve communication between Proxmox and the Ubuntu virtual machine.

---

# Why Install the Guest Agent?

Benefits include:

- Displays the virtual machine IP address inside Proxmox
- Allows clean shutdowns and reboots
- Improves monitoring
- Provides additional guest information to the hypervisor

---

# Installation

Updated Ubuntu packages.

Installed:

```
qemu-guest-agent
```

Enabled the service.

Started the service.

Enabled the Guest Agent within the Proxmox VM Options menu.

---

# Verification

Confirmed:

- Service running
- Guest Agent enabled
- IP address visible in the Proxmox Summary page

IPv4

```
192.168.1.243
```

---

# Lessons Learned

Without the Guest Agent, Proxmox has limited visibility into the guest operating system. Installing the agent significantly improves management capabilities.

---

# Next Steps

Configure a permanent IP address reservation.