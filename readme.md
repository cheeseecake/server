# Server

## Adding New Application Containers

1. Create a folder for the application e.g. `/my-app`, and add a `compose.yml` file inside.

2. In the root `compose.yml`, under `include:`, add the location of the `compose.yml` file above.

3. In Nginx Proxy Manager, add that application as a Proxy Host.

## Immmich

Updating versions:

```sh
docker compose pull immich-server immich-machine-learning immich-redis immich-database
docker compose up -d --force-recreate --remove-orphans immich-server immich-machine-learning immich-redis immich-database
```
