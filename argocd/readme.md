# ArgoCD

Installed following [ArgoCD documentation](https://argo-cd.readthedocs.io/en/stable/getting_started/) and not using helm.
Exposed following their guide with traefik.

## Installation

1. Run `kube create namespace argocd`
2. Run `kube apply -n argocd -f install.yml`
3. Create your ingress using ingress of choice.\

Follow the installation steps thoroughly.

## ERR_TOO_MANY_REDIRECTS

Argo handles https redirect itself by default. To fix edit the configmap like:\
`kubectl edit configmap -n argocd argocd-cmd-params-cm -o yaml`\
and add `server.insecure: "true"` in the data key.\
After that run `kubectl rollout restart -n argocd deployment argocd-server` to make sure Argo reloads the settings and it should be fixed.
