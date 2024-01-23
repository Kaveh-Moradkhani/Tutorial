## Introduction to Docker, Image, and Container

### Docker:
Docker is a platform that enables the packaging, distribution, and execution of applications within isolated environments called containers. Containers encapsulate an application and its dependencies, ensuring consistent and reliable execution across various computing environments.

### Docker Image
A Docker image is a lightweight, standalone, and executable package that includes all the necessary components to run a software application, including code, runtime, libraries, and system tools. Images serve as a snapshot of a specific environment, allowing developers to create reproducible and portable application deployments.

In scientific terms, Docker images can be likened to a versioned and immutable representation of a file system, capturing the configuration, dependencies, and application code in a single unit. This promotes consistency and ease of deployment across different computing environments.

### Container
A Docker container is an instance of a Docker image. Containers provide a consistent and isolated runtime environment for applications, ensuring that they operate consistently across various infrastructure and deployment scenarios. Each container shares the same operating system kernel but runs in isolated user spaces, enabling efficient resource utilization and minimizing conflicts between applications.

In scientific terms, Docker containers implement lightweight virtualization through operating system-level virtualization. They leverage features like cgroups and namespaces to isolate processes and resources, creating an environment where applications can run independently without interfering with each other.

### Docker Basics

#### Quick Docker Installation on Ubuntu:
```
$ sudo apt update
$ sudo apt install -y docker.io
$ sudo systemctl start docker
$ sudo systemctl enable docker
$ docker --version
```

#### Docker Image Commands
- List Docker images
```
$ docker image ls

```

#### Docker Volume Commands
 - List Docker volumes
```
$ docker volume ls
```
#### Docker Container Lifecycle
- Run a Docker container (e.g., Redis)
```
$ docker run redis
```
- List running containers
 ```
$ docker container ls
 ```
- List all containers (including stopped)
```
$ docker container ls -a
```
- Remove a container
```
$ docker container rm reglim-con
```
#### Managing Containers
- Run a detached container with a specific name
```
$ docker run -d --name C1 redis
```
- Stop a running container
```
  $ docker container stop C1
```
- Start a stopped container
```
$ docker container start C1
```
- Restart a container
```
$ docker container restart C1
```

#### Container Inspection
- View detailed information about a container
```
$ docker container inspect C1
```
#### Docker Logging
- View container logs
```
$ docker logs C1
```
- Follow container logs in real-time
```
$ docker logs -f C1
```
#### Docker Hub
- Search for a Docker image on Docker Hub
```
$ docker search mongo
```
- Pull a Docker image from Docker Hub
```
$ docker pull mongo
```

#### Container Management
- Rename a container
```
$ docker container rename C1 C-redis
```
- Monitor container resource usage
```
$ docker stats
```
- Display running processes in a container
```
$ docker container top C-redis
```
#### Executing Commands in Containers 
- Execute a command in a running container
```
$ docker exec C-redis ls
```
- Execute a command in a running container with bash
```
$ docker exec C-redis bash -c "echo 'text string!' > textfile"
```
- Execute an interactive bash shell in a running container
```
$ docker exec -i -t C-redis bash
```
#### Container File System 
- Show changes to files in a container
```
$ docker diff C-redis
```

- Copy files or directories from the host to a container
```
$ docker cp ./text-file C-redis:/usr/test-file
```

### Docker Image Management
#### Build a Docker Image
- Builds a Docker image from a Dockerfile located in the current directory and tags it with a specified name and tag
```
$ docker build -t custom-image:tag .
```
#### Push Docker Image to Docker Hub
- Pushes a locally built Docker image to Docker Hub, making it available for others to use
```
$ docker push username/custom-image:tag
```

### Docker Networking
#### View Docker Networks
- Lists Docker networks, showing the network IDs and names
```
$ docker network ls
```
#### Create a Custom Docker Network
- Creates a custom Docker network for containers to communicate with each other
```
$ docker network create custom-network
```

### Docker Compose 
#### Docker Compose Up 
- Starts Docker containers defined in a `docker-compose.yml` file in detached mode
```
$ docker-compose up -d
```
#### Docker Compose Down
- Stops and removes Docker containers, networks, and volumes defined in a docker-compose.yml file
```
$ docker-compose down
```
### Docker Volume Management
#### Inspect Docker Volume
- Displays detailed information about a Docker volume, including its mount point and configuration
```
$ docker volume inspect volume-name
```
#### Prune Unused Volumes
- Removes all unused Docker volumes, freeing up storage space
```
$ docker volume prune
```
### Docker Swarm (For Orchestration)
#### Initialize Docker Swarm
- Initiates a Docker Swarm, enabling features for container orchestration
```
$ docker swarm init
```
### Deploy Stack in Docker Swarm
- Deploys a Docker stack to a Swarm cluster using a `docker-compose.yml` file
```
$ docker stack deploy -c docker-compose.yml stack-name
```

  

