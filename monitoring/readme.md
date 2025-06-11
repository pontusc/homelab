# Monitoring stack

Grafana & prometheus deployed under namespace monitoring

## Grafana

Install using `helm install -n monitoring grafana grafana/grafana -f grafana-values.yml`\
Update using the grafana-values.yml file, run `helm upgrade -n monitoring grafana grafana/grafana -f grafana-values.yml`\
\
OLD - New credentials stored using sealed-secret\
Username is admin, to get login run `kubectl get secret --namespace monitoring grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo`\

## Prometheus

Install using `helm install prometheus prometheus-community/prometheus -n monitoring --values prometheus-values.yml`\
Update using the values file, run `helm upgrade -n monitoring prometheus prometheus-community/prometheus -f prometheus-values.yml`

## Loki

Install using `helm install loki grafana/loki -n monitoring -f loki-values.yml`

### Loki "too many open file" error

See [this topic](https://askubuntu.com/questions/162229/how-do-i-increase-the-open-files-limit-for-a-non-root-user/162230#162230). You have to configure the node to allow whatever number of file descriptors you want. Can check on nodes with `ulimit -n`

## Alloy

Install using `helm install alloy grafana/alloy -n monitoring -f alloy-values.yml`

## Uptimekuma

Install using `helm install -n monitoring uptime-kuma uptime-kuma/uptime-kuma -f kuma-values.yml`
Update using `helm upgrade -n monitoring uptime-kuma uptime-kuma/uptime-kuma -f kuma-values.yml`
