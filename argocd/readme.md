# ArgoCD
Installed following [ArgoCD documentation](https://argo-cd.readthedocs.io/en/stable/getting_started/) and not using helm.
Exposed following their guide with traefik.

# Installation
Create ```kube create namespace argocd``` and then ```kube apply -n argocd -f install.yml```\
Edit the configmap argocd-cmd-params-cm, e.g. ```kube edit -n argocd configmap argocd-cmd-params-cm``` and add ```data:\server.insecure: "true"```.\
After this the server needs to be restarted using ```kube rollout restart -n argocd deployment argocd-server```
