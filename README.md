# mywayoflearning-Docker

1.** Containers: Core Concepts**
•	Containers package applications with dependencies while sharing the host OS kernel.
•	Provide isolation using namespaces (PID, network, mount, IPC, UTS).
•	Control resources using cgroups.
•	Use layered filesystems for efficient storage.
•	Lightweight, portable, fast to start, ideal for microservices and CI/CD.                                                                                                                                                                                                                                                                                                                                                2. **Docker: Platform Overview**
•	Docker Engine runs containers.
•	Docker Daemon manages images and containers.
•	Docker CLI provides command-line control.
•	Docker Registry stores and distributes images.
•	Used in DevOps for consistent builds, reproducible deployments, and microservice workflows.

3.** Docker Images & Dockerfile Essentials**
•	Images are read-only templates built in layers.
•	Key Dockerfile instructions:
•	  FROM – base image
•	  WORKDIR – working directory
•	  COPY – copy files
•	  RUN – install dependencies
•	  CMD – default command
•	  ENTRYPOINT – main executable
•	  EXPOSE – document ports
•	  ENV – environment variables
•	Best practices: multi-stage builds, minimal base images, optimized layer order, .dockerignore usage.

4. **Container Lifecycle Commands**
•	docker run image – start container
•	docker run -d – run in background
•	docker run -p host:container – port mapping
•	docker run -v host:container – volume mount
•	docker ps – list running containers
•	docker ps -a – list all containers
•	docker stop container – stop
•	docker start container – start
•	docker rm container – remove
•	docker logs container – view logs
•	docker exec -it container bash – open shell

5. **Image Management Commands**
•	docker build -t name:tag . – build image
•	docker images – list images
•	docker pull image – download
•	docker push image – upload
•	docker rmi image – remove
•	docker inspect image/container – metadata                                                                                                                                                                                                      
6. **Docker Networking**
•	Network modes: bridge, host, none, user-defined.
•	Containers on same user-defined network communicate by name.
•	Port mapping exposes container ports to host.

7. **Volumes & Persistence**
•	Types: named volumes, bind mounts.
•	Commands: docker volume create, ls, inspect, rm.
•	Used for databases, logs, persistent data.

8. **Docker Compose**
•	Orchestrates multi-container applications.
•	Supports networking, volumes, environment variables, dependencies.
•	Commands: docker-compose up -d, down, logs, exec.

9. **Security Essentials**
•	Avoid running as root.
•	Use minimal base images.
•	Scan images for vulnerabilities.
•	Keep secrets out of images.
•	Use .dockerignore to avoid leaking sensitive files.

10. Common Troubleshooting Scenarios
•	Container exits immediately: CMD/ENTRYPOINT issue.
•	App unreachable: port mapping or network misconfiguration.
•	Image too large: multi-stage builds, smaller base images.
•	Code changes not reflected: cached layers or volume override.
•	Permission denied on volume: user mismatch.
•	Containers cannot communicate: wrong network or DNS issue.



