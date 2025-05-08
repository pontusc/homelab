Place file in /var/lib/rancher/k3s/server/manifests/traefik-config.yml

# Install missing CRDs
kubectl apply -f https://raw.githubusercontent.com/traefik/traefik/v2.10/docs/content/reference/dynamic-configuration/kubernetes-crd-definition-v1.yml
