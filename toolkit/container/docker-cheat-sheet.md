# Docker Cheat Sheet

My most common `docker` command\
Reference: [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)

```bash
# Create
docker build -t my-tag # Build an image from a Dockerfile and tag it

# Remote
docker login my-registry # Log in to a Docker registry
docker pull my-image # Pull an image (repo) from a registry
docker push my-image # Push an image (repo) to a registry

# Work
docker ps # List containers
docker images # List images

docker run -it ubuntu bash # Run a command in a new container(image=ubuntu) as interactive shell
docker exec -it my-container bash # Run a command in a running container(my-container) as interactive shell

docker start my-container # Start stopped container
docker stop my-container # Stop running container
docker kill my-container # kill running container

# Cleanup
docker rm -f my-container # Force remove container
docker rmi -f my-image # Force remove image

```
