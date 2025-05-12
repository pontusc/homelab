# Information about homelab
Base setup is k3s default install

## Components
 - Ingress: traefik
 - Certs: cert-manager
 - CSI: longhorn
 - GitOps (TODO): *ArgoCD*
 - Monitoring (TODO): Grafana stack

## TODO
Longhorn backups\
Grafana stack and integrate monitoring\
Uptime kuma deployment for all apps\
Add ArgoCD and restructure repo to an apps/***-deployment folder structure\
Make a landingpage for homelab environment, with links to all services (populate automatically?)

## Troubleshooting reminders for myself
Check logs for failing pods with -p flags to see previous containers logs.
Helm lint -f to inspect values files
