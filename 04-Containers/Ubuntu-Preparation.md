# Ubuntu Preparation

## Objective

Prepare the Ubuntu Server virtual machine for Docker by updating the operating system, removing any conflicting Docker packages, and installing the required prerequisite packages.

---

## Environment

| Item | Value |
|------|-------|
| Host | docker-01 |
| Operating System | Ubuntu Server 26.04 LTS |
| Purpose | Docker Host VM |

---

## Steps Performed

### 1. Remove Legacy Docker Packages

Checked for and removed any previously installed Docker packages that could conflict with Docker's official packages.

```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do
    sudo apt remove -y $pkg
done
```

No conflicting packages were installed.

---

### 2. Update Package Lists

Updated the package index to ensure the latest package information was available.

```bash
sudo apt update
```

---

### 3. Install Prerequisite Packages

Installed the packages required to securely add Docker's official repository.

```bash
sudo apt install -y ca-certificates curl gnupg
```

Installed packages:

- ca-certificates
- curl
- gnupg

---

## Verification

Confirmed that:

- Package lists updated successfully.
- Required prerequisite packages installed without errors.
- No legacy Docker packages remained on the system.

---

## Screenshot

See:

```
Photos/01-ubuntu-preparation.png
```

---

## Lessons Learned

- Docker recommends removing distribution-provided Docker packages before installing Docker Engine from the official repository.
- Installing the latest package metadata helps prevent dependency issues.
- Preparing the system first makes the Docker installation process more reliable.

---

## Next Step

Continue by adding Docker's official APT repository before installing Docker Engine.