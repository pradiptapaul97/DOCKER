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

### 4. `docker run`
**Description**: Create and start a container from an image. This command is the primary way to launch applications in Docker.

**Common Flags**:
- `-d`: Run container in the background (detached mode).
- `-p`: Publish a container's port(s) to the host (e.g., `8080:80`).
- `--name`: Assign a custom name to your container for easier management.
- `-it`: Interactive mode (interactive + TTY), useful for shell access.
- `--rm`: Automatically remove the container when it exits.

**Examples**:
```bash
# Run an Nginx web server in the background on port 8080
docker run -d -p 8080:80 --name my-web-server nginx

# Run a Node.js container with a custom name
docker run --name my-node-app node

# Run Node.js interactively with a custom name
docker run -it --name pradipta_node node
```

**What this command does**:
- **Finds the image**: Checks if the `node` image exists locally; if not, it pulls it from Docker Hub.
- **Creates the container**: Sets up a new container instance from the image.
- **Assigns a name**: Names the container `my-node-app` instead of using a random string.
- **Starts the process**: Executes the default entrypoint for the Node.js image.

---

### 5. `docker start`
**Description**: Start one or more stopped containers. This is used when you already have a container created (via `run` or `create`) but it is currently in a stopped state.

**Example**:
```bash
# Start a container by its name
docker start my-web-server

# Start a container by its ID
docker start 1a2b3c4d5e6f
```

---

## 💡 `docker run` vs `docker start`

Understanding the difference between these two is crucial for efficient container management:

| Feature | `docker run` | `docker start` |
| :--- | :--- | :--- |
| **Primary Action** | Creates a **NEW** container and starts it. | Restarts an **EXISTING** stopped container. |
| **Source** | Uses an **Image**. | Uses a **Container ID/Name**. |
| **Effect** | Every execution creates a fresh instance. | Resumes the state of a specific instance. |
| **Typical Use** | Initial deployment or testing. | Resuming work on a persistent container. |

> [!IMPORTANT]
> Use `docker run` when you want a new container. Use `docker start` when you want to bring an old container back to life.

---

> [!TIP]
> You can combine flags for more powerful queries, such as `docker ps -aq` to get only the IDs of all containers.

---

### 6. `docker attach`
**Description**: Attach your local standard input, output, and error streams to a running container. This allows you to view its output or interact with it in real-time.

**Example**:
```bash
docker attach my-web-server
```

> [!TIP]
> To detach from a container without stopping it, use the escape sequence `Ctrl+P`, `Ctrl+Q`.

---

### 7. `docker ps`
**Description**: List running containers. Use the `-a` flag to see all containers (including stopped ones).

**Example**:
```bash
# List only running containers
docker ps

# List all containers (running and stopped)
docker ps -a
```

---