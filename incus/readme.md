# Incus

Uses incus for virtualized nodes. Running one control node and two worker nodes with Ubuntu 22.04 LTS.

## Setup

Run:

- `incus launch images:ubuntu/22.04 control-1 --profile k3s-control --vm`
- `incus launch images:ubuntu/22.04 worker-X --profile k3s-worker --vm`

Edit the netplan configs of all images to follow this structure:

```yaml
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
      nameservers:
        addresses:
          - 1.1.1.1
          - 192.168.1.1
      dhcp-identifier: mac
```

Install K3S following their documentation, grab the token and install on both agents.
This can and should be automated using Ansible, will explore that tool later when I need to automate VM management.

## Profiles

Incus profiles used

### Control node

```yaml
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

```yaml
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

## MISSING REQUIREMENTS

Stuff I have had to change manually after deploying, that should be included in cloud-init or some other way.

- Dependencies for Longhorn\
  Open-iscsi (services iscsid and open-iscsi need to be enabled and started)
- File descriptor limit\
  Default seems to be 1024, and that is not enough when running Loki. See topic under [monitoring](/monitoring) and Loki error.
