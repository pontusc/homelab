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

## K3S Configurations

If you only want certain nodes to have the load balancer, label one or more with `vccontroller.k3s.cattle.io/enablelb=true`

Change the default storageclass provided by K3S to not be default. Run below or edit yourself on control node.

```bash
sudo sed -i -e "s/storageclass.kubernetes.io\/is-default-class: \"true\"/storageclass.kubernetes.io\/is-default-class: \"false\"/g" /var/lib/rancher/k3s/server/manifests/local-storage.yml
```

This can be pre-configured when installing K3S, if you already know you are going to use longhorn. I think changing the file directly should work, but K3S might repopulate this file n restart of server based on some other behaviour, so double-check.
