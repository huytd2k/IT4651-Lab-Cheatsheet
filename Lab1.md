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

## Turn off default firewall rules
```bash
iptables -D FORWARD -j REJECT --reject-with icmp-host-prohibited
```

## Checking iptable rules
```bash
iptables -L -n
```

## Add NAT routing
```bash
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
```

## Change NIC name in `/etc/udev/rules.d/70-persistent-net.rules`