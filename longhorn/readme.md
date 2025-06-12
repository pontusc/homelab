# Longhorn

Installed using `helm install longhorn longhorn/longhorn -n longhorn-system --create-namespace --values values.yaml`

## Node requirements

Open-iscsi (services iscsid and open-iscsi need to be enabled and started)

## Prometheus Operator for Longhorn metrics

Get the CRD's from [here](https://prometheus-operator.dev/docs/getting-started/installation/#install-using-yaml-files)

## Missing CRDs

If you receive log errors regarding voluemsnapshotclasses... missing, see [this](https://longhorn.io/docs/archives/1.1.1/snapshots-and-backups/csi-snapshot-support/enable-csi-snapshot-support/). Install CRD's from [here](https://github.com/kubernetes-csi/external-snapshotter).
