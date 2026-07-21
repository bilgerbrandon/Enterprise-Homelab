# Docker Installation

## Objective

Install Docker Engine and Docker Compose using Docker's official APT repository, then verify that the Docker service is running correctly.

---

## Environment

| Item | Value |
|------|-------|
| Host | docker-01 |
| Operating System | Ubuntu Server 26.04 LTS |
| Docker Version | 29.6.2 |
| Docker Compose Version | 5.3.1 |

---

## Steps Performed

### 1. Add Docker's Official Repository

Created the keyring directory, imported Docker's GPG key, configured the official Docker repository, and updated the package index.

```bash
sudo install -m 0755 -d /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
```

---

### 2. Install Docker Engine

Installed Docker Engine, Docker CLI, Containerd, Buildx, and the Docker Compose plugin.

```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Installed components:

- Docker Engine (`docker-ce`)
- Docker CLI (`docker-ce-cli`)
- containerd
- Docker Buildx
- Docker Compose Plugin

---

### 3. Verify Installation

Verified the installed versions.

```bash
docker --version

docker compose version
```

Example output:

```
Docker version 29.6.2
Docker Compose version 5.3.1
```

---

### 4. Verify Docker Service

Confirmed that the Docker daemon was running.

```bash
sudo systemctl status docker
```

The service reported an **active (running)** status.

---

### 5. Run Test Container

Executed Docker's official Hello World container.

```bash
sudo docker run hello-world
```

Docker successfully:

- Downloaded the image
- Created the container
- Started the container
- Displayed the Hello World message

This verified that Docker was installed and functioning correctly.

---

## Verification

The installation was considered successful after confirming:

- Docker Engine installed successfully
- Docker Compose plugin installed
- Docker service running
- Hello World container executed without errors

---

## Screenshots

- `Photos/02-docker-repository-added.png`
- `Photos/03-docker-installation.png`
- `Photos/04-docker-version.png`
- `Photos/05-docker-service.png`
- `Photos/06-hello-world.png`

---

## Lessons Learned

- Installing Docker from the official Docker repository ensures access to the latest stable releases.
- Docker Engine, Buildx, and Docker Compose are installed as separate packages.
- Running the Hello World container provides a quick end-to-end validation that the Docker daemon, networking, and image downloads are functioning correctly.

---

## Next Step

Install Portainer to provide a web-based interface for managing Docker containers, images, volumes, and networks.