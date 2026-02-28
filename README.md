
1.**What a container actually is** 

-A container is a runtime instance of a Docker image. An image is the blueprint; the container is the running process created from that blueprint. It uses the host machine’s kernel but keeps its own isolated filesystem, network stack, and process space.
This isolation is achieved through Linux features such as namespaces (for isolation) and cgroups (for resource limits).

2.**Why containers exist**

-Containers solve a classic problem: “It works on my machine, but not on yours.”
They ensure:
- Consistency — same environment everywhere (dev, test, prod).
- Portability — run on any machine with Docker installed.
- Isolation — one app doesn’t interfere with another.
- Efficiency — much lighter than virtual machines because they don’t need a full OS

 3.**What’s inside a container**
 -A container typically includes:
- Application code (e.g., Python, Node.js, Java)
- Runtime (e.g., Python interpreter, JVM)
- Required libraries and dependencies
- Configuration (environment variables, ports)
- A minimal filesystem (from the image

 It does not include:
- A full operating system
- A separate kernel

4.**Container vs Virtual Machine**
<img width="868" height="351" alt="image" src="https://github.com/user-attachments/assets/9a13a310-6c41-4d2d-98fa-4c49c438f163" /> 

5.**How containers are used in real scenarios**
- Running microservices (e.g., separate containers for API, DB, frontend)
- Packaging and shipping applications
- CI/CD pipelines
- Cloud deployments (Kubernetes, ECS)
- Local development environments
  
6.**Core technologies behind containers:**
- Namespaces (process, network, mount, PID isolation)
- cgroups (resource limits)
- Union file systems (layered images

 7.**What Docker Is**
-Docker is a platform that:
- Builds container images.
- Runs containers.
- Manages container lifecycle.
- Provides registries to store and share images.
  
 8.**Docker components**:
- Docker Engine — runtime that executes containers.
- Docker CLI — command-line interface.
- Docker Daemon — background service managing containers.
- Docker Hub / Registry — image storage.

9.**Docker Images**
 A Docker image is a read-only template used to create containers. It contains:
- Base OS layer (e.g., Alpine, Ubuntu)
- Application runtime (Node, Python, Java)
- Application code
- Dependencies
 Images are built using a Dockerfile, which defines:
- Base image (FROM)
- Commands to install dependencies (RUN)
- Files to copy (COPY)
- Working directory (WORKDIR)
- Ports (EXPOSE)
- Startup command (CMD or ENTRYPOINT)
 Images are layered, meaning:
- Each instruction creates a new layer.
- Layers are cached to speed up builds.
- Reusing layers reduces image size.

10.**Dockerfile Essentials**
Common instructions:
- FROM — base image
- WORKDIR — set working directory
- COPY — copy files into image
- RUN — execute commands during build
- CMD — default command when container starts
- ENTRYPOINT — main executable for the container
- EXPOSE — document port
- ENV — environment variables
- USER — run container as non-root
- .dockerignore — exclude files from build context

 11.**Container Lifecycle**
Typical lifecycle:
- Build image → docker build
- Run container → docker run
- Stop container → docker stop
- Start again → docker start
- Remove container → docker rm
- Remove image → docker rmi

 12.**Core Docker Commands (Interview Must-Know)**
Image Commands
- docker build -t name:tag . — build image
- docker images — list images
- docker pull image — download image
- docker push image — upload image
- docker rmi image — remove image
Container Commands
- docker run image — run container
- docker run -d — run in background
- docker run -p host:container — map ports
- docker run -v host:container — mount volumes
- docker ps — list running containers
- docker ps -a — list all containers
- docker stop container — stop
- docker start container — start
- docker rm container — remove
- docker logs container — view logs
- docker exec -it container bash — enter container shell
Debugging Commands
- docker inspect container — detailed info
- docker logs container — check errors
- docker exec -it container sh — debug inside container
- docker events — monitor Docker daemon

 13.**Docker Networking Basics**
Docker provides:
- Bridge network (default)
- Host network (shares host network)
- None (no network)
- User-defined networks (recommended)
Key concepts:
- Containers on the same user-defined network can communicate by name.
- Port mapping (-p) exposes container ports to the host.

 14.**Docker Volumes**
Volumes persist data beyond container lifecycle.
Types:
- Named volumes — managed by Docker
- Bind mounts — map host directory to container
Commands:
- docker volume create
- docker volume ls
- docker volume inspect
- docker volume rm
Use cases:
- Databases
- Logs
- Config files

15.**Docker Compose Basics**
Compose manages multi-container applications using a docker-compose.yml file.
Common commands:
- docker-compose up -d — start all services
- docker-compose down — stop and remove
- docker-compose logs — view logs
- docker-compose exec service bash — enter service shell
Compose features:
- Service orchestration
- Networking between services
- Environment variables
- Volume management

16.**Security Basics**
Important practices:
- Avoid running as root inside containers.
- Use minimal base images (Alpine, Distroless).
- Scan images for vulnerabilities.
- Do not store secrets in images.
- Use .dockerignore to avoid leaking sensitive files.

17.**Common Interview Scenarios**
- Container exits immediately → entrypoint or CMD issue.
- App not reachable → port mapping or network issue.
- Image too large → multi-stage builds, smaller base image.
- Code changes not reflected → volume mount overriding or cached layers.
- Permission denied on volume → user mismatch between host and container.









 





