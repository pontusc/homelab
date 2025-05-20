# Monitoring stack
Grafana & prometheus deployed under namespace monitoring

## Grafana
Install using ```helm repo add grafana https://grafana.github.io/helm-charts```\
Update using the grafana-values-helm.yml file, run ```helm upgrade -n monitoring grafana grafana/grafana -f grafana-values-helm.yml```\
Username is admin, to get login run ```kubectl get secret --namespace monitoring grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo```\

## Prometheus
Install using ```helm install prometheus prometheus-community/prometheus -n monitoring --values prometheus-values-helm.yml```\
Update using the values file, run ```helm upgrade -n monitoring prometheus prometheus-community/prometheus -f prometheus-values-helm.yml```
