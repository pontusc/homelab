# Homelab setup
Base setup is k3s default install.\
Running on a single NUC, with virtualized nodes (soon).\
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

## TODO
Current structure is k3s hosted on a single node. Will change for k3s to run on 1 manager node and 2 worker nodes, which will be running on 3 vm's to simulate a "real" environment. 

## Troubleshooting reminders for myself
Check logs for failing pods with -p flags to see previous containers logs in case of CrashLoopback...
Helm lint -f to inspect values files
