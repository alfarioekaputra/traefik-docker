# Running the Traefik Container

```markdown
$ docker network create web
```

```
    docker run -d \
        -v /var/run/docker.sock:/var/run/docker.sock \
        -v $PWD/traefik.toml:/traefik.toml \
        -p 80:80 \
        -l traefik.frontend.rule=Host:monitor.example.com \
        -l traefik.port=8080 \
        --network proxy \
        --name traefik \
        traefik:1.7.16-alpine --docker

```