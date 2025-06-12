# Longhorn

Installed using `helm install longhorn longhorn/longhorn -n longhorn-system --create-namespace --values values.yaml`

## Node requirements

Open-iscsi (services iscsid and open-iscsi need to be enabled and started)

## Prometheus ServiceMonitor for Longhorn metrics

See [monitoring](/monitoring) and install the kube-prometheus-stack helm chart. You have to add the label `release=kube-prometheus-stack` for it to be discovered.

## Missing CRDs

If you receive log errors regarding voluemsnapshotclasses... missing, see [this](https://longhorn.io/docs/archives/1.1.1/snapshots-and-backups/csi-snapshot-support/enable-csi-snapshot-support/). Install CRD's from [here](https://github.com/kubernetes-csi/external-snapshotter).
