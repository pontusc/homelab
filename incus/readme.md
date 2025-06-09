# Incus
Uses incus for virtualized nodes. Running one controlnode and two worker nodes with Ubuntu22.04 LTS.

## Setup
Run:
 - ```incus launch images:ubuntu/22.04 control-1 --profile k3s-control --vm```
 - ```incus launch images:ubuntu/22.04 worker-X --profile k3s-worker --vm```

Edit the netplan configs of all images to follow this structure:
```
network:
  version: 2
  ethernets:
    enp5s0:
      dhcp4: false
      addresses:
        - 192.168.1.XXX/24
      routes:
        - to: default
          via: 192.168.1.1
      dhcp-identifier: mac
```

Install K3S following their documentation, grab the token and install on both agents.

## Profiles
Incus profiles used

### Control node
```
config:
  boot.autostart: "true"
  boot.autostart.priority: "10"
  limits.cpu: "2"
  limits.memory: 8GB
  limits.memory.swap: "false"
description: Profile for K3S control plane node
devices:
  eth0:
    name: eth0
    nictype: bridged
    parent: br0
    type: nic
  root:
    path: /
    pool: default
    size: 150GB
    type: disk
name: k3s-control
```

### Worker node
```
config:
  boot.autostart: "true"
  boot.autostart.priority: "5"
  limits.cpu: "4"
  limits.memory: 8GB
  limits.memory.swap: "false"
description: Profile for K3S worker nodes
devices:
  eth0:
    name: eth0
    nictype: bridged
    parent: br0
    type: nic
  root:
    path: /
    pool: default
    size: 150GB
    type: disk
name: k3s-worker
```
