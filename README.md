# Docker Cheat Sheet

## Containers

```bash
# Run container in background
docker run -d --name container_name image_name

# List running containers
docker ps

# List all containers (including stopped ones)
docker ps -a

# Stop container
docker stop container_name

# Remove container
docker rm container_name

# Interactive shell inside running container
docker exec -it container_name /bin/bash
```

## Images

```bash
# Build image from Dockerfile
docker build -t image_name:tag .

# Build image using BuildKit
DOCKER_BUILDKIT=1 docker build -t image_name:tag .

# List local images
docker images

# Remove image
docker rmi image_name
```

## Cleanup

```bash
# Remove stopped containers, unused networks, and dangling images
docker system prune

# Prune all unused images, containers, networks, and volumes
docker system prune -a --volumes
```

## Logs & Inspection

```bash
# View container logs with tailing
docker logs -f --tail 100 container_name

# Monitor live stream of container resource usage
docker stats

# Inspect detailed container info
docker inspect container_name
```