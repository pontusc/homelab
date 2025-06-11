# Authentik

Used to authenticate for access to certain services on the cluster.

## Installation

Follow [this guide](https://docs.goauthentik.io/docs/install-config/install/kubernetes).\
Install using `helm install authentik authentik/authentik -f authentik-values.yml -n authentik`\
Update using `helm upgrade -n authentik authentik authentik/authentik -f authentik-values.yml`

## Configuration

Setup a forward auth service (proxy) in authentik, and apply the middleware for traefik.
