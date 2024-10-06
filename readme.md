# Server

## Adding New Application Containers

1. Create a folder for the application e.g. `/my-app`, and add a `compose.yml` file inside.

1. In the root `compose.yml`, add a Tailscale service container, using the template below (replace all occurences of `my-app`):

```yml
ts-my-app:
    <<: *tailscale
    container_name: ts-my-app
    hostname: my-app # Name that you will access your container on the browser by
    volumes:
    - /dev/net/tun:/dev/net/tun
    - ./tailscale/my-app:/var/lib/tailscale # Don't forget to create this folder in the /tailscale directory
```

1. Also in the root `compose.yml`, add your app's `compose.yml` under the `include:` section.

1. `docker compose up -d` and access your container at `http://my-app:<port>` (you may need to configure your app to run on port 80).

## Immmich

Updating versions:

```sh
docker compose pull immich-server immich-machine-learning immich-redis immich-database
docker compose up -d --force-recreate --remove-orphans immich-server immich-machine-learning immich-redis immich-database
```