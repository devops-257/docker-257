# Docker 257

Compose files that mainly support Docker Swarm, as well as `docker compose`.

## Philosophy

- [Docker Swarm](https://docs.docker.com/engine/swarm/)
- [Docker Compose](https://docs.docker.com/compose/)
- GitOps
- One-step startup powered by [Task](https://taskfile.dev/)
- Reverse proxy powered by [Traefik](https://traefik.io)
- Auto HTTPS powered by [Traefik](https://traefik.io)
- Utility compose files each [override](https://docs.docker.com/compose/multiple-compose-files/merge/) less configuration
- [12-factor](https://12factor.net/)

## Usage

### 1. Run manually

1. Clone this repo to any machine that can connect to Docker daemon
2. `docker stack` or `docker compose` to deploy

### 2. GitOps Automation

You can use this git repo directly. It is recommended to use [Portainer](https://www.portainer.io/gitops-automation) to implement GitOps.

## Configuration

It's not recommended to modify project's compose files. If you want to change something, it is better to create a new compose file to override fields. For example:

```bash
vim stacks/compose.portainer.override.yaml
docker stack deploy -c stack/compose.portainer.yaml -c stacks/compose.portainer.override.yaml
```
