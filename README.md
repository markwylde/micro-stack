# Init a swarm
```bash
docker swarm init
```

# Create the networks
```bash
docker network create --driver overlay --scope swarm --attachable --opt encrypted web
docker network create --driver overlay --scope swarm --attachable --opt encrypted traefik
docker network create --driver overlay --scope swarm --attachable --opt encrypted consul
```

# Create the services
```bash
docker stack up -c consul-config.yml consul
docker stack up -c traefik-config.yml traefik
docker stack up -c portainer-config.yml portainer
```
