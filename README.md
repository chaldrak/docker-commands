# docker-commands

Here’s a curated list of essential Docker commands and concepts, grouped by functionality. While it’s impossible to list **every** command (due to flags, subcommands, and updates), this covers the most common ones:

---

### **Container Management**
1. **Run a container**:
   ```bash
   docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
   # Example:
   docker run -d --name my_container -p 8080:80 nginx
   ```
   - `-d`: Detached mode (run in background).
   - `--name`: Assign a name.
   - `-p`: Map ports (host:container).
   - `-v`: Mount volumes.
   - `-e`: Set environment variables.

2. **List containers**:
   ```bash
   docker ps          # List running containers
   docker ps -a       # List all containers (including stopped)
   ```

3. **Start/Stop/Restart**:
   ```bash
   docker start CONTAINER
   docker stop CONTAINER
   docker restart CONTAINER
   ```

4. **Remove containers**:
   ```bash
   docker rm CONTAINER    # Remove a stopped container
   docker rm -f CONTAINER # Force remove (running)
   ```

5. **Interact with containers**:
   ```bash
   docker exec -it CONTAINER COMMAND   # Execute a command in a running container
   docker attach CONTAINER             # Attach to a running container
   docker logs CONTAINER               # View logs
   ```

6. **Inspect containers**:
   ```bash
   docker inspect CONTAINER   # Detailed metadata
   docker stats               # Live resource usage
   docker top CONTAINER       # View running processes
   ```

---

### **Image Management**
1. **Build an image**:
   ```bash
   docker build -t TAGNAME PATH
   # Example:
   docker build -t myapp:latest .
   ```

2. **List images**:
   ```bash
   docker images
   docker image ls
   ```

3. **Pull/Push images**:
   ```bash
   docker pull IMAGE:TAG      # Download from registry
   docker push IMAGE:TAG      # Upload to registry
   ```

4. **Remove images**:
   ```bash
   docker rmi IMAGE           # Remove an image
   docker image prune         # Remove unused images
   ```

5. **Save/Load images**:
   ```bash
   docker save -o FILE.tar IMAGE   # Save image to a tar file
   docker load -i FILE.tar         # Load image from tar file
   ```

---

### **Networks**
1. **Create/Manage networks**:
   ```bash
   docker network create NETWORK_NAME
   docker network ls           # List networks
   docker network inspect NETWORK
   docker network rm NETWORK
   ```

2. **Connect containers to networks**:
   ```bash
   docker network connect NETWORK CONTAINER
   docker network disconnect NETWORK CONTAINER
   ```

---

### **Volumes**
1. **Manage volumes**:
   ```bash
   docker volume create VOLUME_NAME
   docker volume ls
   docker volume inspect VOLUME
   docker volume rm VOLUME
   ```

---

### **Docker Compose**
1. **Start services**:
   ```bash
   docker-compose up -d      # Start in detached mode
   docker-compose down       # Stop and remove containers/networks
   ```

2. **Build/Manage**:
   ```bash
   docker-compose build      # Rebuild images
   docker-compose logs       # View logs
   docker-compose ps         # List services
   ```

---

### **Docker Swarm (Orchestration)**
1. **Initialize Swarm**:
   ```bash
   docker swarm init
   docker swarm join-token worker  # Get join token
   ```

2. **Manage services**:
   ```bash
   docker service create --name SERVICE_NAME IMAGE
   docker service ls
   docker service scale SERVICE=REPLICAS
   ```

---

### **System & Cleanup**
1. **System info**:
   ```bash
   docker info          # Docker engine details
   docker version       # Version info
   ```

2. **Cleanup**:
   ```bash
   docker system prune         # Remove unused data (images, containers, networks)
   docker system prune -a      # Remove all unused images
   ```

---

### **Useful Shortcuts**
- `docker rm -f $(docker ps -aq)`: Force-remove all containers.
- `docker rmi $(docker images -q)`: Remove all images.
- `docker exec -it CONTAINER sh`: Start a shell in a running container.

---

### **Documentation**
- Use `--help` for any command:  
  ```bash
  docker run --help
  docker build --help
  ```
- Official Docker Docs: [https://docs.docker.com/](https://docs.docker.com/)

Kindly built by **Le Dev Matheux** 😊🩷
