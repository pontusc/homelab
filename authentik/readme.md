# Authentik
Used to authenticate for access to certain services on the cluster.

## Installation
Following [this guide](https://docs.goauthentik.io/docs/install-config/install/kubernetes).\
Install running ```helm install authentik authentik/authentik -f authentik-values.yml -n authentik```\
Update using ```helm upgrade -n authentik authentik authentik/authentik -f authentik-values.yml```

## Configuration
Setup a forward auth provider for traefik using the website interface, and it will also automatically create the corresponding traefik middleware.
