# DHCP Reservation

## Objective

Assign a permanent IP address to the Docker virtual machine using a DHCP reservation.

---

# Why DHCP Reservation?

Rather than configuring a static IP address directly inside Ubuntu, the router reserves an IP address for the VM based on its MAC address.

Advantages include:

- Centralized management
- Easier rebuilds
- Prevents duplicate IP addresses
- Simplifies future server migrations

---

# Configuration

Hostname

docker-01

Reserved Address

192.168.1.243

MAC Address

BC:24:11:74:07:3D

---

# Verification

Verified:

- Reservation enabled on the router
- VM consistently receives the reserved address
- Proxmox displays the correct IP address

---

# Lessons Learned

DHCP reservations combine the flexibility of DHCP with the consistency of static addressing, making them ideal for homelab servers.

---

# Next Steps

Document the overall IP addressing plan.