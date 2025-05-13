# Homepage
Uses [homepage](https://gethomepage.dev/) as a homepage for the cluster, with links to all services.
Maps all config files against host. Will not work on clusters of more than one node unless you specify the node with files it is allowed to deploy on. Should be put in a PV instead, future improvement when adding GitOps.\
For icons see [dashboardicons.com](https://dashboardicons.com/).

## Autodiscovery
See [this](https://gethomepage.dev/configs/kubernetes/) for information. Separate annotation requirements for Ingress objects vs traefiks IngressRoute objects.\
Decided to not use this, except for actual deployments. Cluster services are specifically added.
