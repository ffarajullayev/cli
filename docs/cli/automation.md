# CLI automation

You can automate the provisioning of the virtual machines via the help of the cli and cloud init [Cloud init reference](https://cloudinit.readthedocs.io/en/latest/). Cloud init is integrated into AzCloud UI and CLI. It allows you to perform post-installation of the virtual machine (assign ip address, install packages).

!!! Apps
    Soon the apps will be available which will include common things like Docker or LAMP stack to be easily installed. They also use the cloud init to install and configure packages.

## Assign ip address
When creating a new virtual machine, you can assign ip address to it using the following metadata:

```yaml
local-hostname: play-node-1
instance-id: play-node-1
network:
  version: 1
  config:
    - type: physical
  name: ens192
  subnets:
    - type: static
  address: 192.168.1.2
  netmask: 255.255.255.0
  gateway: 192.168.1.254
```
!!! Note
    This configuration works for Centos systems with cloud init installed (by default all Linux systems templates).
We need to change the address and gateway to our needs.

## Install custom package
You can install custom packages (please note internet should be available there) using the following userdata script:

```yaml
# Update apt database on first boot
package_update: true
# Install additional packages on first boot
packages:
    - nginx
    - nodejs
    - npm
    - python3.6
```

## Run any bash command
Additionally, you can run virtually any bash command in userdata section:

```yaml
# Runcmd will only run during the first boot
runcmd:
    - echo 192.168.1.1 test.com >> /etc/hosts
    - echo "Everything completed" >> /etc/log
```