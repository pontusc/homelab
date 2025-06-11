# Homelab setup

Base setup is k3s default install.\
Running on a single NUC, with virtualized nodes.\
See [nejlikka.com](https://nejlikka.com).

## Core components

- Kubernetes: [K3S](https://docs.k3s.io)
- Management: [Rancher](https://github.com/rancher/rancher)
- Ingress: [Traefik](https://github.com/traefik/traefik/)
- Certs: [Cert-manager](https://github.com/cert-manager/cert-manager)
- CSI: [Longhorn](https://github.com/longhorn/longhorn)
- CNI: [Flannel](https://github.com/flannel-io/flannel)
- Monitoring: [Grafana](https://github.com/grafana/grafana)
- TSDB: [Prometheus](https://github.com/prometheus/prometheus)
- LogDB: [Loki](https://github.com/grafana/loki)
- GitOps: [ArgoCD](https://github.com/argoproj/argo-cd)
  - [Sealed-secrets](https://github.com/bitnami-labs/sealed-secrets)
  - [Reloader](https://github.com/stakater/Reloader)

## Deployments

- [Homepage](https://github.com/pontusc/homepage)
- [Aboutme](https://github.com/pontusc/aboutme)
- [Ntfy](https://github.com/pontusc/homelab/deployments/ntfy)
