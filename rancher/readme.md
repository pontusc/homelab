# Rancher
Using latest rancher-stable release through helm.\
\
Install using ```helm install rancher rancher-stable/rancher -n cattle-system --create-namespace -f rancher-values.yml```\
Update/ugrade using ```helm upgrade -n cattle-system rancher rancher-stable/rancher -f rancher-values.yml```
