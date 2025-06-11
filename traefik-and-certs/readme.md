# Cert-manager and traefik

## Traefik update

To update traefik values run `kube apply -f traefik-values.yml`. K3S can also automatically apply helm chart values if you set it up following [this documentation](https://docs.k3s.io/helm#customizing-packaged-components-with-helmchartconfig)

## Traefik config

All incoming traffic on entrypint web(port 80) gets redirected to websecure(port 443).\
Default wildcard certificate is active.\

Middleware configured in middleware-traefik.yml.\

## Cert-manager install

Run `kubectl apply -f cert-manager.yml`.\
After that, add the cloudflare secret, and the cloudflare-le-issuer.\
Once complete, add the wildcard-default-cert and make sure it manages to achieve a ready state.

## Cert-manager config

Two ClusterIssuers configured.

- selfsigned-clusterissuer uses selfmade certficate, not in use.
- cloudflare-le-clusterissuer uses cloudflare and letsencrypt to resolve challenges, default to use.

## Troubleshooting traefik helm updates

If wrong format on values file, the helm-install-traefik pod will get stuck in a CrashLoopError.\
Check using `kube logs -n kube-system -p helm-install-traefik-xxxxx` to see what the previous pod reported as error.
