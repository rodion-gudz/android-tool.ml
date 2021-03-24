---
title: Docker Installation
layout: default
parent: Installation
nav_order: 1
---

# {{ page.title }}

In order to host on desktop Linux, you can use Podman or Docker. Simply run the following command in a shell:

```
podman pull registry.gitlab.com/friendly-telegram/friendly-telegram && podman run -itv "$(pwd)":/data:Z -p ${PORT:-8080}:8080 $(curl -s https://gitlab.com/friendly-telegram/friendly-telegram/-/raw/master/Dockerfile.modules | podman build -qf- -v "$(pwd)":/data:Z)
```

Command breakdown:
 - `podman pull registry.gitlab.com/friendly-telegram/friendly-telegram`
   Download latest images from the [registry](https://gitlab.com/friendly-telegram/friendly-telegram/container_registry)
 - `curl -s https://gitlab.com/friendly-telegram/friendly-telegram/-/raw/master/Dockerfile.modules | podman build -qf- -v "$(pwd)":/data:Z`
   Fetch latest module addition builder and run it (this installs dependencies for dynamically loaded modules to the docker image)
 - `podman run -itv "$(pwd)":/data:Z -p ${PORT:-8080}:8080`
   Run the generated image

When you want to restart the userbot, simply run the command again - it will automatically check for and install updates

If you can't use podman and would prefer to use docker, simply find and replace `podman` to `docker` in the command
