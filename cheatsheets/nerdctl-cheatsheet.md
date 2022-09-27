# nerdctl Cheat Sheet

My most common `nerdctl` command\
Reference: [nerdctl CLI](https://github.com/containerd/nerdctl)

```bash
# Namespace
nerdctl namespace ls # List namespaces

# Create
nerdctl build -t my-tag # Build an image from a Dockerfile and tag it

# Remote
nerdctl login my-registry # Log in to a registry
nerdctl pull my-image # Pull an image (repo) from a registry
nerdctl push my-image # Push an image (repo) to a registry

# Work
nerdctl ps # List containers
nerdctl images # List images
nerdctl tag src-image:tag target-image:tag # Create a tag target-image from src-image

nerdctl run -it ubuntu bash # Run a command in a new container(image=ubuntu) as interactive shell
nerdctl exec -it my-container bash # Run a command in a running container(my-container) as interactive shell

nerdctl start my-container # Start stopped container
nerdctl stop my-container # Stop running container
nerdctl kill my-container # kill running container

# Cleanup
nerdctl rm -f my-container # Force remove container
nerdctl rmi -f my-image # Force remove image

```
