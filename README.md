# Traefik with Docker Compose

This is a simple boilerplate project for setting up traefik with docker and docker compose.

## Deployment

To make this project run and work for you follow some easy steps,

## Clone the repo:

```bash
git clone https://github.com/RilusMahmud/traefik-docker.git
```

### Make necessary changes:

Make sure in data folder `acme.json` file permission is set to `600`

Run this command to update the permission for the file

```bash
sudo chmod 600 data/acme.json
```

Also make necessary change as the Host and DNS

```
- "traefik.http.routers.traefik.rule=Host(`change.me`)"
```

Also make sure you use the preferred certresolver

```
- "traefik.http.routers.traefik-secure.tls.certresolver=production"
```

### Finally:

Create docker network named `proxy` (or any name you prefer, also then you have to update the network in docker-compose file)

```bash
docker network create proxy
```

Now run docker compose command

```bash
docker compose up -d
```

Voila!!

## Authors

- [@rilusmahmud](https://github.com/RilusMahmud)
