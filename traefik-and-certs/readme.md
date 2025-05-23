# Cert-manager and traefik

## Traefik update
Just run ```kube apply -f traefik-values.yml```. This needs to be cleaned up

## Traefik config
All incoming traffic on entrypint web(port 80) gets redirected to websecure(port 443).\
Default wildcard certificate is active.\
Middlewares exist for redirecting as well, but most likely not needed with default redirect active.\

Traefik configured in traefik-values.yml\
Middleware configured in middleware-traefik.yml\
Certs stored under certs/

## Cert-manager config
Two ClusterIssuers configured.
 - selfsigned-clusterissuer uses selfmade certficate, not in use.
 - cloudflare-le-clusterissuer uses cloudflare and letsencrypt to resolve challenges, default to use.

## Troubleshooting traefik helm updates
If wrong format on values file, the helm-install-traefik pod will get stuck in a CrashLoopError\
Check using kube logs -n kube-system -p helm-install-traefik-***** to see what the previous pod reported as error
