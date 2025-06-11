# GitOps

All manifests for each deployment managed via Argo are located here.\
See each respective folder for more information.

## Flow

Argo monitors each folder under deployments/ and will reconcile current state on the cluster with state in the manifests here. Each deployment gets updated via a pipeline in their respective repository that pushes changes here. Any changes to this repository utilizes the Argo webhook to trigger a refresh, which automatically syncs the deployments.
