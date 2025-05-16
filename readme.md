# Information about homelab
Base setup is k3s default install

## Components
 - Management: Rancher
 - Ingress: traefik
 - Certs: cert-manager
 - CSI: longhorn
 - CNI: flannel
 - Monitoring: Grafana stack
 - GitOps: ArgoCD

## Services
 - Homepage
 - Emby (TODO)

## TODO
Longhorn backups\
Uptime kuma deployment for all apps\
Add ArgoCD and restructure repo to an apps/***-deployment folder structure\

## Troubleshooting reminders for myself
Check logs for failing pods with -p flags to see previous containers logs.
Helm lint -f to inspect values files
