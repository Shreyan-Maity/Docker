# Docker Commands Cheat Sheet

Docker commands are versatile and provide a range of functionality, from container and image management to networking and system diagnostics. Here’s a comprehensive list of commonly used Docker commands with explanations:

## 1. Basic Docker Commands

### `docker --version`
- **Description**: Displays the version of Docker installed on your system.

### `docker info`
- **Description**: Displays detailed information about the Docker installation, including the number of containers and images, storage drivers, network settings, etc.

### `docker help`
- **Description**: Lists all available Docker commands or displays help for a specific command when used with `docker help [command]`.

## 2. Working with Images

### `docker images`
- **Description**: Lists all Docker images on your system.
- **Options**:
  - `-a` or `--all`: Shows all images, including intermediate images.
  - `-q` or `--quiet`: Displays only image IDs.

### `docker pull [image-name]:[tag]`
- **Description**: Downloads an image from Docker Hub or a private registry.
- **Example**: `docker pull nginx:latest`

### `docker rmi [image-id or image-name]`
- **Description**: Removes one or more images from the local system.
- **Options**:
  - `-f` or `--force`: Forces the removal of the image.

### `docker tag [source-image] [target-image]`
- **Description**: Tags an image with a new name.
- **Example**: `docker tag ubuntu:latest myrepo/ubuntu:v1`

### `docker build -t [image-name]:[tag] .`
- **Description**: Builds a Docker image from a `Dockerfile` in the current directory.
- **Options**:
  - `-t` or `--tag`: Tags the image with a name and optional tag.
- **Example**: `docker build -t myapp:latest .`

## 3. Working with Containers

### `docker run [options] [image-name]`
- **Description**: Runs a command in a new container based on an image.
- **Options**:
  - `-d` or `--detach`: Runs the container in detached mode (in the background).
  - `-p [host-port]:[container-port]`: Maps a container port to a host port.
  - `--name [container-name]`: Assigns a name to the container.
  - `-e [environment-variable]=[value]`: Sets environment variables.
- **Example**: `docker run -d -p 8080:80 --name mynginx nginx:latest`

### `docker ps`
- **Description**: Lists all running containers.
- **Options**:
  - `-a` or `--all`: Shows all containers, including stopped ones.
  - `-q` or `--quiet`: Displays only container IDs.

### `docker stop [container-id or container-name]`
- **Description**: Stops a running container.

### `docker start [container-id or container-name]`
- **Description**: Starts a stopped container.

### `docker restart [container-id or container-name]`
- **Description**: Restarts a running container.

### `docker rm [container-id or container-name]`
- **Description**: Removes one or more containers.
- **Options**:
  - `-f` or `--force`: Forces removal of the container.
  - `-v` or `--volumes`: Removes any volumes associated with the container.

### `docker exec [options] [container-name or container-id] [command]`
- **Description**: Runs a command in a running container.
- **Options**:
  - `-it`: Allows interaction with the container (used for bash shell access).
- **Example**: `docker exec -it mynginx bash`

## 4. Managing Container Logs and Stats

### `docker logs [container-id or container-name]`
- **Description**: Displays logs of a specific container.
- **Options**:
  - `-f` or `--follow`: Follows the log output.
  - `-t` or `--timestamps`: Shows timestamps.

### `docker stats [container-id or container-name]`
- **Description**: Displays real-time resource usage statistics for one or more containers.

### `docker top [container-id or container-name]`
- **Description**: Shows running processes within a container, similar to the `top` command on Linux.

## 5. Container Networking

### `docker network ls`
- **Description**: Lists all Docker networks.

### `docker network create [network-name]`
- **Description**: Creates a new Docker network.
- **Options**:
  - `--driver [driver]`: Specifies the network driver (e.g., `bridge`, `host`, `overlay`).

### `docker network connect [network-name] [container-name]`
- **Description**: Connects a container to an existing network.

### `docker network disconnect [network-name] [container-name]`
- **Description**: Disconnects a container from a network.

### `docker network inspect [network-name]`
- **Description**: Displays detailed information about a specific network.

## 6. Volume Management

### `docker volume ls`
- **Description**: Lists all Docker volumes on the system.

### `docker volume create [volume-name]`
- **Description**: Creates a new Docker volume.

### `docker volume rm [volume-name]`
- **Description**: Removes a specific Docker volume.

### `docker volume inspect [volume-name]`
- **Description**: Displays detailed information about a volume.

## 7. Docker System Commands

### `docker system df`
- **Description**: Shows the amount of disk space used by images, containers, and volumes.

### `docker system prune`
- **Description**: Removes unused data, including stopped containers, networks, dangling images, and build cache.
- **Options**:
  - `--volumes`: Also removes unused volumes.

### `docker save -o [output-file.tar] [image-name]`
- **Description**: Saves an image to a tar archive file, which can be transferred to other systems.

### `docker load -i [input-file.tar]`
- **Description**: Loads an image from a tar archive file.

## 8. Advanced Commands

### `docker commit [container-id] [new-image-name]:[tag]`
- **Description**: Creates a new image from a container’s changes.
- **Example**: `docker commit mycontainer mynewimage:v1`

### `docker inspect [container-id or image-id]`
- **Description**: Returns low-level information about a container or an image in JSON format.

### `docker export [container-id] -o [output-file.tar]`
- **Description**: Exports a container's filesystem as a tar archive, useful for backups or migrations.

### `docker import [input-file.tar] [new-image-name]:[tag]`
- **Description**: Imports the contents of a tar file to create a new filesystem image.

## 9. Docker Compose (Multi-Container Applications)

### `docker-compose up`
- **Description**: Starts services defined in a `docker-compose.yml` file.
- **Options**:
  - `-d` or `--detach`: Runs containers in detached mode.

### `docker-compose down`
- **Description**: Stops and removes containers, networks, and volumes defined in the `docker-compose.yml` file.

### `docker-compose ps`
- **Description**: Lists containers managed by Docker Compose.

### `docker-compose logs`
- **Description**: Displays log output from services defined in the `docker-compose.yml` file.
- **Options**:
  - `-f` or `--follow`: Follows log output.

---

This guide covers essential Docker commands to help you get started with managing containers, images, networks, volumes, and more in Docker.
