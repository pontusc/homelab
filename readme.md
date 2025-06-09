# Homelab setup
Base setup is k3s default install.\
Running on a single NUC, with virtualized nodes.\
See [nejlikka.com](https://nejlikka.com).

## Components
 - Management: Rancher
 - Ingress: traefik
 - Certs: cert-manager
 - CSI: longhorn
 - CNI: flannel
 - Monitoring: Grafana stack (loki TBA)
 - GitOps: ArgoCD
 - Secrets: Sealed-secrets

## Deployments
 - [Homepage](https://github.com/pontusc/homepage)
 - [Aboutme](https://github.com/pontusc/aboutme)
