![alt text](image.png)

# 🐳 Docker Reference Guide

A comprehensive guide to essential Docker commands for managing containers and images efficiently.

---

## 🛠️ Essential Commands

### 1. `docker version`
**Description**: Display the Docker version information, including client and server details. Use this to verify your installation and check compatibility.

**Example**:
```bash
docker version
```

---

### 2. `docker images`
**Description**: List all locally stored Docker images. This command shows the repository name, tag, image ID, creation date, and size.

**Example**:
```bash
docker images
```

---

### 3. `docker pull`
**Description**: Download an image from a registry (typically Docker Hub) to your local machine.

**Syntax**:
```bash
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```

**Example**:
```bash
# Pull the latest version of the official Nginx image
docker pull nginx:latest
```

---

### 4. `docker ps`
**Description**: List running containers. Use the `-a` flag to see all containers (including stopped ones).

**Example**:
```bash
# List only running containers
docker ps

# List all containers (running and stopped)
docker ps -a
```

---

> [!TIP]
> You can combine flags for more powerful queries, such as `docker ps -aq` to get only the IDs of all containers.