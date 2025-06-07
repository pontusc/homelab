# Reloader
Tool used to refresh pod deployments when you only update a secret or configmap via ArgoCD.
See [reloader](https://github.com/stakater/Reloader)

## Useage
Add label to any deployment (for secrets and configmaps) like below:\
```yml
reloader.stakater.com/auto: "true"
```

## Install
Installed by following their helm installation guide and specifying namespace reloader.
