# Docker

Docker is an open platform for developing, shipping, and running applications.

## Docker Platform

Docker provides the ability to package and run an application in a loosely isolated environment called a container.

## Docker Engine

Major components:

- A server which is a type of long-running program called a daemon process (the `dockerd` command)
- A REST API which specified interfaces that programs can use to talk to the daemon and instruct it what to do
- A command line interface (CLI) client (the `docker` command)

![docker-engine](https://docs.docker.com/engine/images/engine-components-flow.png)

## Docker Architecture

![docker-architecture](https://docs.docker.com/engine/images/architecture.svg)

Docker *daemon*: `dockerd` listens for Docker API requests and manages Docker objects(images, containers, network, and volumes).\
Docker *client*: `docker` is where users interact with Docker and it uses Docker API.\
Docker *registries*: `registry` stores Docker images, Docker is configured to look for images on Docker Hub dy default.\
Docker *objects*:

- Images (read-only template with instructions for creating a Docker container)
- Containers (runnable instance of an image)
- Services (scale containers across multiple Docker daemons)
