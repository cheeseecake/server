# Server

## Immmich

Updating versions:

```sh
docker compose pull immich-server immich-machine-learning immich-redis immich-database
docker compose up -d --force-recreate --remove-orphans immich-server immich-machine-learning immich-redis immich-database
```