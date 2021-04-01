# Lab01

## Centos config folder
`/etc/sysconfig/network-scripts`


## DHCP config

```bash
DEVICE=eth0
BOOTPROTO=dhcp
ONBOOT=yes
```

## Reload network config
```bash
$ service network restart
```

## Enable IP Fordwarding
### Persitent config in `/etc/sysctl.conf`

```bash
$ sysctl -w net.ipv4.ip_forward=1
```