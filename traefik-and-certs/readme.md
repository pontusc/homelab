# Cert-manager and traefik

## Troubleshooting traefik helm updates
If wrong format on values file, the helm-install-traefik pod will get stuck in a CrashLoopError
Check using kube logs -n kube-system -p helm-install-traefik-***** to see what the previous pod reported as error
