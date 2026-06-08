# Docker Compose Stack

![Docker](https://img.shields.io/badge/Docker-Containers-2496ED)
![Docker Compose](https://img.shields.io/badge/Docker%20Compose-v2-blue)
![YAML](https://img.shields.io/badge/YAML-1.2-lightgrey)

This repository holds a collection of Docker Compose YAML files used as parts of the current service stack. The compose files are stored in the `ComposeFiles/` directory. Each `compose_*.yaml` file defines one service or a small group of services that you can run independently or together to assemble the full environment.

## What The Stack Is For

 - Provides reproducible service configurations for local development, testing, and lightweight deployments.
 - Lets you start individual services (e.g., Nextcloud, Immich, Watchtower) without running the entire environment.
 - Acts as a catalog of curated compose files you can adapt for your projects.

## Why This Is Useful

 - Quick way to spin up a single service with all its dependencies.
 - Versioned YAML files make configuration explicit and portable.
 - Useful for demos, local labs, and composing small multi-container setups.

## Repository Structure

- `ComposeFiles/`: directory containing the compose YAML files used by this stack.

Contents of `ComposeFiles/`:

- [ComposeFiles/compose_aliasvault.yaml](ComposeFiles/compose_aliasvault.yaml)
- [ComposeFiles/compose_arr.yaml](ComposeFiles/compose_arr.yaml)
- [ComposeFiles/compose_fmd.yaml](ComposeFiles/compose_fmd.yaml)
- [ComposeFiles/compose_forgejo.yaml](ComposeFiles/compose_forgejo.yaml)
- [ComposeFiles/compose_immich.yaml](ComposeFiles/compose_immich.yaml)
- [ComposeFiles/compose_kuma.yaml](ComposeFiles/compose_kuma.yaml)
- [ComposeFiles/compose_molly.yaml](ComposeFiles/compose_molly.yaml)
- [ComposeFiles/compose_nextcloud.yaml](ComposeFiles/compose_nextcloud.yaml)
- [ComposeFiles/compose_nginxpm.yaml](ComposeFiles/compose_nginxpm.yaml)
- [ComposeFiles/compose_ollama.yaml](ComposeFiles/compose_ollama.yaml)
- [ComposeFiles/compose_snapotter.yaml](ComposeFiles/compose_snapotter.yaml)
- [ComposeFiles/compose_stalwart.yaml](ComposeFiles/compose_stalwart.yaml)
- [ComposeFiles/compose_watchtower.yaml](ComposeFiles/compose_watchtower.yaml)

Each file in `ComposeFiles/` is focused on a single service or related set of services — inspect the file to see the containers, volumes, networks, and environment variables that it defines.

## How To Get Started

### Prerequisites

 - Docker Engine (compatible with Docker Compose v2)
 - Optional: `docker-compose` CLI if you prefer it over the built-in `docker compose`

### 1) Choose a Compose File

Pick the service you want to run from the list above (for example `ComposeFiles/compose_nextcloud.yaml`).

### 2) Start The Service

Run one of these commands from the repository root:

```bash
# using Docker Compose v2 (recommended)
docker compose -f ComposeFiles/compose_nextcloud.yaml up -d

# or, if you have the separate docker-compose binary
docker-compose -f ComposeFiles/compose_nextcloud.yaml up -d
```

### 3) Stop And Remove

```bash
docker compose -f ComposeFiles/compose_nextcloud.yaml down
```

Replace `compose_nextcloud.yaml` above with whichever file you want to run.

## Quick Usage Example

1. Start a service: `docker compose -f ComposeFiles/compose_nextcloud.yaml up -d`.
2. Inspect logs: `docker compose -f ComposeFiles/compose_nextcloud.yaml logs -f`.
3. Stop the stack: `docker compose -f ComposeFiles/compose_nextcloud.yaml down`.

## Where To Get Help

- Docker docs: https://docs.docker.com/
- Docker Compose: https://docs.docker.com/compose/

## Maintainers And Contributions

Maintainer:

- [@kydoa](https://github.com/kydoa)
