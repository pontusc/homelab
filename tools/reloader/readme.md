# Reloader

Tool used to refresh pod deployments when you only update a secret or configmap via ArgoCD.
See [reloader](https://github.com/stakater/Reloader)

## Useage

Add annotation to any deployment (for secrets and configmaps) like below:

```yml
reloader.stakater.com/auto: "true"
```

Should be under

```yaml
metadata.annotations:
```

## Install

Installed by following their helm installation guide and specifying namespace reloader.
