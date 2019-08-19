# Overview

\* Useful summary of [Docker overview](https://docs.docker.com/engine/docker-overview/)

Docker is an open platform for developing, shipping, and running applications.

## Docker Platform

Docker provides the ability to package and run an application in a loosely isolated environment called a container.

## Docker Engine

Major components:

- A server which is a type of long-running program called a daemon process (the `dockerd` command)
- A REST API which specified interfaces that programs can use to talk to the daemon and instruct it what to do
- A command line interface (CLI) client (the `docker` command)

![docker-engine](https://docs.docker.com/engine/images/engine-components-flow.png)

Next: [Architecture](01-architecture.md)
