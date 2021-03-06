alpine-traefik 
==============

This image is the traefik base. It comes from rawmind/alpine-monit.

## Build

```
docker build -t rawmind/alpine-traefik:<version> .
```

## Versions

- `1.0.0-beta.555` [(Dockerfile)](https://github.com/rawmind0/alpine-traefik/blob/master/Dockerfile)


## Configuration

This image runs [traefik][traefik] with monit. Besides, you can customize the configuration in several ways:

### Default Configuration

Traefic is installed with the default configuration and some parameters can be overrided with env variables:

- TRAEFIK_HTTP_PORT
- TRAEFIK_ADMIN_PORT

### Custom Configuration

Traefik is installed under /opt/traefik and make use of /opt/traefik/etc/traefik.toml and /opt/traefik/etc/rules.toml.

You can edit this files in order customize configuratin

You could also include FROM rawmind/alpine-traefik at the top of your Dockerfile, and add your custom config.

### Rancher

If you are running it in rancher, you could run [rancher-traefik][rancher-traefik] as a sidekick to get dynamic configuration.


## Example

See [rancher-example][rancher-example], that run a traefik lb in all infrastructure servers and publish ${TRAEFIK_HTTP_PORT} and ${TRAEFIK_ADMIN_PORT} throught them.


## TODO

Add https automation to the traefik.


[traefik]: https://github.com/containous/traefik
[rancher-traefik]: https://hub.docker.com/r/rawmind/rancher-traefik/
[rancher-example]: https://github.com/rawmind0/alpine-traefik/tree/master/rancher
