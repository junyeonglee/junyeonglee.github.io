# Architecture

\* Useful summary of [Docker architecture](https://docs.docker.com/engine/docker-overview/)

## Docker Architecture

![docker-architecture](https://docs.docker.com/engine/images/architecture.svg)

### Docker *daemon*

`dockerd` listens for Docker API requests and manages Docker objects(images, containers, network, and volumes).

### Docker *client*

`docker` is where users interact with Docker and it uses Docker API.

### Docker *registries*

`registry` stores Docker images, Docker is configured to look for images on Docker Hub dy default.

### Docker *objects*

- Images (read-only template with instructions for creating a Docker container)
- Containers (runnable instance of an image)
- Services (scale containers across multiple Docker daemons)
