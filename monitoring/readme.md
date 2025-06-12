# Monitoring stack

Grafana & prometheus deployed under namespace monitoring

## Kube-prometheus-stack

Install using `helm install -n monitoring kube-prometheus-stack prometheus-community/kube-prometheus-stack -f stack-values.yml`.

Installs Grafana, Prometheus, Prometheus-Operator and some more, see [this](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack). Also brings a lot of necessary CRD's for stuff like ServiceMonitor.

## Grafana

Migrated to Kube-prometheus-stack

## Prometheus

Migrated to Kube-prometheus-stack

## Alloy

Install using `helm install alloy grafana/alloy -n monitoring -f alloy-values.yml`

## Uptimekuma

Install using `helm install -n monitoring uptime-kuma uptime-kuma/uptime-kuma -f kuma-values.yml`
Update using `helm upgrade -n monitoring uptime-kuma uptime-kuma/uptime-kuma -f kuma-values.yml`

## Loki

Install using `helm install loki grafana/loki -n monitoring -f loki-values.yml`

### Loki "too many open file" error

See [this topic](https://askubuntu.com/questions/162229/how-do-i-increase-the-open-files-limit-for-a-non-root-user/162230#162230). You have to configure the node to allow whatever number of file descriptors you want. Can check on nodes with `ulimit -n`.\

Above fix did not remove issue completely, and I also edited my `fs.inotify` values.

```bash
# Add to sysctl configuration
sudo tee -a /etc/sysctl.conf << EOF
# Increase inotify limits for container workloads
fs.inotify.max_user_instances = 512
fs.inotify.max_user_watches = 524288
fs.inotify.max_queued_events = 32768
EOF

# Apply the changes
sudo sysctl -p
```
