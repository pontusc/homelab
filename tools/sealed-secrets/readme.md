# Sealed Secrets
Uses [sealed-secrets](https://github.com/bitnami-labs/sealed-secrets) to manage secrets for ArgoCD.
Installed using ```helm install sealed-secrets -n kube-system --set-string fullnameOverride=sealed-secrets-controller sealed-secrets/sealed-secrets``` so kubeseal doesnt require additional args.

## Kubeseal
Install using ```go install github.com/bitnami-labs/sealed-secrets/cmd/kubeseal@main```, requires go pkg manager installed.
